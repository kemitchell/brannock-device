#!/usr/bin/env ruby
# frozen_string_literal: true

tsv = `./tsv`

split = tsv.split("\n")
column_widths = []
split.each do |line|
  line.split("\t").each_with_index do |cell, column|
    width = cell.length + 2
    column_widths[column] = width if column_widths[column].nil? || width > column_widths[column]
  end
end

header = split[0]
print '|'
print header.split("\t").each_with_index.map { |x, column| " #{x} ".ljust(column_widths[column]) }.join('|')
print "|\n"

print '|'
print header.split("\t").each_with_index.map { |x, column| ('-' * (x.length + 2)).ljust(column_widths[column], '-') }.join('|')
print "|\n"

split[1..].each do |line|
  print '|'
  print line.split("\t").each_with_index.map { |x, column| " #{x}".ljust(column_widths[column]) }.join('|')
  print "|\n"
end
