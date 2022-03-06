# Slater Condon tools
Tools to evaluate the [Slater Condon rules](https://en.wikipedia.org/wiki/Slater%E2%80%93Condon_rules) for quantum determinants and multideterminants.

Create Slater determinants:

    >>> triplet = det2(nel=4,mult=3)
    >>> triplet
    |aa̅bc>

Evaluate energy expressions:

    >>> triplet.energy()
    2haa + hbb + hcc + Jaa + 2Jab - Kab + 2Jac - Kac + Jbc - Kbc

Create multi-determinant wave functions, e.g. open shell singlets:

    >>> oss = MultiDet(det("aabc"),det("aacb"))
    >>> oss
    |aa̅bc̅> + |aa̅cb̅>
    >>> oss.normalize()
    >>> oss
    0.70711|aa̅bc̅> + 0.70711|aa̅cb̅>
    >>> oss.energy()
    2haa + hbb + hcc + Jaa + 2Jab - Kab + 2Jac - Kac + Jbc

