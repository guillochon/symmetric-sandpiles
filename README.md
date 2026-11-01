# Symmetric Sandpiles — OEIS A348567

**https://guillochon.github.io/symmetric-sandpiles/**

[A348567](https://oeis.org/A348567) counts the recurrent configurations of the abelian sandpile on the n × n grid
that look the same under all eight symmetries of the square: 1, 4, 2, 32, 12, 832, 232, 69632, … for n = 0, 1, 2, ….
The OEIS listed a(0)–a(10), along with a conjecture linking them to [A348566](https://oeis.org/A348566). The count
is a product of eigenvalues,

    a(n) = ∏ over odd h ≤ k ≤ n of (4 − 2cos(hπ/(n+1)) − 2cos(kπ/(n+1))),

which proves the conjecture and gives every term. The proof, the checks and the table to n = 100 are in
[oeis-results/A348567](https://github.com/guillochon/oeis-results/tree/main/A348567).

The page has three figures and the table of terms:

- **The identity.** The recurrent identity of the n × n grid (it has all eight symmetries), recomputed by toppling
  sand in the browser for any n up to 200. The switch dims everything except the 1/8 wedge that determines a
  symmetric configuration.
- **All of them, for small n.** Every fully symmetric recurrent configuration for n = 2..6, sorted by number of
  grains; the identity and the all-3s pile are outlined. The number of tiles is a(n).
- **Why it is a product.** The symmetric eigenpatterns of the grid Laplacian, one for each pair of odd frequencies
  h ≤ k, each labelled with its eigenvalue; their product is a(n).

## How it works

Everything runs in the browser, in one file (`index.html`).

- **Identity.** e = (6 − (6)°)°, where 6 is the all-6s pile and ° means stabilize (topple until every cell has at
  most 3 grains).
- **Gallery.** All 4^m configurations that are constant on the m symmetry orbits, each tested for recurrence with
  Dhar's burning algorithm.
- **Eigenmodes.** f(i, j) = sin(hiπ/(n+1))·sin(kjπ/(n+1)) + sin(kiπ/(n+1))·sin(hjπ/(n+1)), coloured blue to orange.
- **Terms.** The exact values a(0)–a(100) are embedded in the page.

Made by James Guillochon with Claude. The source lives in the oeis-sniper project (`viz/A348567/`); this repo holds
the published copy.
