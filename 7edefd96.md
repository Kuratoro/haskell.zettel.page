---
title: Deriving instances for GADTs
date: "2020-05-25"
tags:
    - gadt
---

`Generic` deriving does not work for <5956fd49?cf>s. You will need to use the following libraries for deriving several key instances:

* [`dependent-sum`](https://github.com/obsidiansystems/dependent-sum) - for deriving Eq, Show, Ord
* [`aeson-gadt-th`](https://hackage.haskell.org/package/aeson-gadt-th) - for deriving JSON instances
  * Use this in conjunction with [`dependent-sum-aeson-orphans`](https://github.com/obsidiansystems/dependent-sum-aeson-orphans) to get instances for `ToJSON (Some f)`

