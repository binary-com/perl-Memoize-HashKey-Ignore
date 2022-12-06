# NAME

Memoize::HashKey::Ignore - allow certain keys not to be memoized.

# SYNOPSIS

    use Memoize;

    tie my %scalar_cache = 'Memoize::HashKey::Ignore', IGNORE => sub { my $key = shift, return ($key eq 'BROKENKEY') ? 1 : 0; };
    tie my %list_cache   = 'Memoize::HashKey::Ignore', IGNORE => sub { my $key = shift, return ($key eq 'BROKENKEY') ? 1 : 0; };

    memoize('function', SCALAR_CACHE => [ HASH => \%scalar_cache ], LIST_CACHE => [ HASH => \%list_cache ]);

# EXPORT

Sometimes you don't want to store certain keys. You know what the values looks likes, but you can't easily write memoize function which culls them itself.

Memoize::HashKey::Ignore allows you to supply a code reference which describes, which keys should not be stored in Memoization Cache.

This module will allow you to memoize the entire function with splitting it into cached and uncached pieces.

# AUTHOR

binary.com, `<rakesh at binary.com>`

# BUGS

Please report any bugs or feature requests to `bug-memoize-hashkey-ignore at rt.cpan.org`, or through
the web interface at [http://rt.cpan.org/NoAuth/ReportBug.html?Queue=Memoize-HashKey-Ignore](http://rt.cpan.org/NoAuth/ReportBug.html?Queue=Memoize-HashKey-Ignore).  I will be notified, and then you'll
automatically be notified of progress on your bug as I make changes.

# SUPPORT

You can find documentation for this module with the perldoc command.

    perldoc Memoize::HashKey::Ignore

You can also look for information at:

- RT: CPAN's request tracker (report bugs here)

    [http://rt.cpan.org/NoAuth/Bugs.html?Dist=Memoize-HashKey-Ignore](http://rt.cpan.org/NoAuth/Bugs.html?Dist=Memoize-HashKey-Ignore)

- AnnoCPAN: Annotated CPAN documentation

    [http://annocpan.org/dist/Memoize-HashKey-Ignore](http://annocpan.org/dist/Memoize-HashKey-Ignore)

- CPAN Ratings

    [http://cpanratings.perl.org/d/Memoize-HashKey-Ignore](http://cpanratings.perl.org/d/Memoize-HashKey-Ignore)

- Search CPAN

    [http://search.cpan.org/dist/Memoize-HashKey-Ignore/](http://search.cpan.org/dist/Memoize-HashKey-Ignore/)

# ACKNOWLEDGEMENTS
