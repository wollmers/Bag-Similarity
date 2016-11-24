# NAME

Bag::Similarity - Similarity measures for bags

<div>
    <a href="https://travis-ci.org/wollmers/Bag-Similarity"><img src="https://travis-ci.org/wollmers/Bag-Similarity.png" alt="Bag-Similarity"></a>
    <a href='https://coveralls.io/r/wollmers/Bag-Similarity?branch=master'><img src='https://coveralls.io/repos/wollmers/Bag-Similarity/badge.png?branch=master' alt='Coverage Status' /></a>
    <a href='http://cpants.cpanauthors.org/dist/Bag-Similarity'><img src='http://cpants.cpanauthors.org/dist/Bag-Similarity.png' alt='Kwalitee Score' /></a>
    <a href="http://badge.fury.io/pl/Bag-Similarity"><img src="https://badge.fury.io/pl/Bag-Similarity.svg" alt="CPAN version" height="18"></a>
</div>

# SYNOPSIS

    use Bag::Similarity;

# DESCRIPTION

Bag::Similarity is the base class for similarity measures of bags.

# METHODS

All methods can be used as class or object methods.

## new

    $object = Bag::Similarity->new();

## similarity

    my $similarity = $object->similarity($any1,$any1,$width);

`$any` can be an arrayref, a hashref or a string. Strings are tokenized into n-grams of width `$width`.

`$width` must be integer, or defaults to 1.

## from\_tokens

    my $similarity = $object->from_tokens(['a','b'],['b']);

## from\_bags

    my $similarity = $object->from_bags(['a'],['b']);

Croaks if called directly. This method should be implemented in a child module.

## intersection

    my $intersection_size = $object->intersection(['a'],['b']);

## combined\_length

    my $set_size_sum = $object->combined_length(['a'],['b']);

## min

    my $min_set_size = $object->min(['a'],['b']);

## ngrams

    my @monograms = $object->ngrams('abc');
    my @bigrams = $object->ngrams('abc',2);

## \_any

    my $arrayref = $object->_any($any,$width);

# AUTHOR

Helmut Wollmersdorfer &lt;helmut.wollmersdorfer@gmail.com>

<div>
    <a href='http://cpants.cpanauthors.org/author/wollmers'><img src='http://cpants.cpanauthors.org/author/wollmers.png' alt='Kwalitee Score' /></a>
</div>

# COPYRIGHT

Copyright 2014-2015 Helmut Wollmersdorfer

# LICENSE

This library is free software; you can redistribute it and/or modify
it under the same terms as Perl itself.

# SEE ALSO
