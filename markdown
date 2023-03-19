#!/usr/bin/env ruby
# frozen_string_literal: true

tsv = `./tsv`
column_width = 11

split = tsv.split("\n")
header = split[0]
print '|'
print header.split("\t").map { |x| " #{x} ".ljust(column_width) }.join('|')
print "|\n"

print '|'
print header.split("\t").map { |x| ('-' * (x.length + 2)).ljust(column_width, '-') }.join('|')
print "|\n"

split[1..].each do |line|
  print '|'
  print line.split("\t").map { |x| " #{x}".ljust(column_width) }.join('|')
  print "|\n"
end
