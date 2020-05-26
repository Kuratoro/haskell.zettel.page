---
title: Deriving instances for GADTs
date: "2020-05-25"
tags:
    - gadt
---

* Eq, Ord, Show can be derived using the `StandaloneDeriving` extension (implicitly using the `stock` deriving strategy). 
* To derive instances for `Some f` (where `f` is your GADT), as well as `DSum f g`, you will need to use the following libraries :

  * [`some`](https://hackage.haskell.org/package/some) and [`dependent-sum`](https://github.com/obsidiansystems/dependent-sum) - for deriving GEq, GShow, GCompare
  * [`aeson-gadt-th`](https://hackage.haskell.org/package/aeson-gadt-th) - for deriving JSON instances
    * Use this in conjunction with [`dependent-sum-aeson-orphans`](https://github.com/obsidiansystems/dependent-sum-aeson-orphans) to get instances for `ToJSON (Some f)`

* The [`kind-generics`](https://hackage.haskell.org/package/kind-generics) package generalizes the approach of `GHC.Generics` to GADTs.
