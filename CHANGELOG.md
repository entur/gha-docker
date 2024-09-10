# Changelog

## [1.3.9](https://github.com/entur/gha-docker/compare/v1.3.8...v1.3.9) (2024-09-10)


### Bug Fixes

* release ([#126](https://github.com/entur/gha-docker/issues/126)) ([5845473](https://github.com/entur/gha-docker/commit/58454730d74d64ec2c87fb2fe405f8451c0266c3))

## [1.3.8](https://github.com/entur/gha-docker/compare/v1.3.7...v1.3.8) (2024-08-30)


### Bug Fixes

* remove environment property ([#119](https://github.com/entur/gha-docker/issues/119)) ([7273c56](https://github.com/entur/gha-docker/commit/7273c569907fce05339c5f57c29fbd6c69a0e93b))

## [1.3.7](https://github.com/entur/gha-docker/compare/v1.3.6...v1.3.7) (2024-08-26)


### Bug Fixes

* add docker auth to build, environment property tbd ([8c0c95a](https://github.com/entur/gha-docker/commit/8c0c95a86cd6ae338e1795954e2cc20543d42407))
* add id-token generation ([#113](https://github.com/entur/gha-docker/issues/113)) ([5bd54a8](https://github.com/entur/gha-docker/commit/5bd54a8a8c08a8c63b35b3cfcb70abfdccc1f195))

## [1.3.6](https://github.com/entur/gha-docker/compare/v1.3.5...v1.3.6) (2024-07-25)


### Bug Fixes

* do not use environment for docker push ([#99](https://github.com/entur/gha-docker/issues/99)) ([ffa8bad](https://github.com/entur/gha-docker/commit/ffa8bad204fe7287ab08f9815cce21fa827d0eb0))

## [1.3.5](https://github.com/entur/gha-docker/compare/v1.3.4...v1.3.5) (2024-06-28)


### Bug Fixes

* enable skip of git tagging ([#96](https://github.com/entur/gha-docker/issues/96)) ([ffbe913](https://github.com/entur/gha-docker/commit/ffbe913ed18b6c270ca698d2f7d0277b16157cf5))

## [1.3.4](https://github.com/entur/gha-docker/compare/v1.3.3...v1.3.4) (2024-06-17)


### Bug Fixes

* add fetch-depth 0 (old pr's) and if pr, ref to pr ([#86](https://github.com/entur/gha-docker/issues/86)) ([baa214e](https://github.com/entur/gha-docker/commit/baa214e40bac0d5b624a58f1e6822a6c27ebebab))

## [1.3.3](https://github.com/entur/gha-docker/compare/v1.3.2...v1.3.3) (2024-06-05)


### Bug Fixes

* GITHUB_REF_NAME if merge ([68dbfe6](https://github.com/entur/gha-docker/commit/68dbfe6b40852cbb684e09803bb7bb221987ac79))
* set default branch name if head ref is not set ([7d6ad92](https://github.com/entur/gha-docker/commit/7d6ad926c33100513b48911ba053c2398438eb3b))
* set default branch name if head ref is not set ([#76](https://github.com/entur/gha-docker/issues/76)) ([2d1b01b](https://github.com/entur/gha-docker/commit/2d1b01b6fe87c53e0f1b60e3af1c6b19619cade1))

## [1.3.2](https://github.com/entur/gha-docker/compare/v1.3.1...v1.3.2) (2024-06-05)


### Bug Fixes

* add force to overwrite tag ([c28ece7](https://github.com/entur/gha-docker/commit/c28ece72862da94ca8069a287827526940f0aabd))
* checkout ([dab9960](https://github.com/entur/gha-docker/commit/dab996010f1349a2691983438fe054d160730a87))
* fetch depth 0 ([56dbbab](https://github.com/entur/gha-docker/commit/56dbbab01d6e44a48c92ab65eccf4a7703787dda))
* new cache method ([556e1a1](https://github.com/entur/gha-docker/commit/556e1a1f6e6b76d92413be09f5eedef49df1bbc6))
* new cache method ([#74](https://github.com/entur/gha-docker/issues/74)) ([e41eae1](https://github.com/entur/gha-docker/commit/e41eae16f2601ffff5be8f7c1ef2782009d1befb))
* push origin ([59c59b1](https://github.com/entur/gha-docker/commit/59c59b154776ec57e9af173d2fbb808c4107e495))
* remove buildx ([0561cc2](https://github.com/entur/gha-docker/commit/0561cc2c21a876c9270c076a174c96e5e78fc602))
* remove gha cache build ([c096cac](https://github.com/entur/gha-docker/commit/c096cacc8af9e92a21a89a354e4fbf9177eb62f2))
* remove harness build ([58adf90](https://github.com/entur/gha-docker/commit/58adf9010b535569c04cb2e826a4033579dd0b8d))
* remove image name from git tag ([7f0a00c](https://github.com/entur/gha-docker/commit/7f0a00c0bd7ca2848e9643b3508b980a29dad82c))
* rolling tag ([6b45114](https://github.com/entur/gha-docker/commit/6b45114280729eac0dd9ba102109d06823c1deee))
* switch to git push --follow-tags ([632d332](https://github.com/entur/gha-docker/commit/632d33216d3f1fde247360944486b3c3f35547d1))
* switch to git push --follow-tags ([511eb24](https://github.com/entur/gha-docker/commit/511eb24a51c8b08140085493c383ce5eb8409bb4))
* try switch ([92109e0](https://github.com/entur/gha-docker/commit/92109e007998976bef48c141f2201347f3de5ba0))
* typo ([169a117](https://github.com/entur/gha-docker/commit/169a1177b2512c11be0c276cf359e3423aadba64))
* upload artifact always, and tag git with image version ([5cba7cd](https://github.com/entur/gha-docker/commit/5cba7cd49b6ee9007ea5e487239bad8c30e8ea5b))

## [1.3.1](https://github.com/entur/gha-docker/compare/v1.3.0...v1.3.1) (2024-06-03)


### Bug Fixes

* tag on push ([#70](https://github.com/entur/gha-docker/issues/70)) ([4cbca6d](https://github.com/entur/gha-docker/commit/4cbca6dfab0d5c22f9b1930867425d409bf0f5bd))

## [1.3.0](https://github.com/entur/gha-docker/compare/v1.2.4...v1.3.0) (2024-05-30)


### Features

* input vars and prevent injections ([#68](https://github.com/entur/gha-docker/issues/68)) ([f05ff4b](https://github.com/entur/gha-docker/commit/f05ff4b4dc06a5ba236fb354968e4030679a644e))

## [1.2.4](https://github.com/entur/gha-docker/compare/v1.2.3...v1.2.4) (2024-05-23)


### Bug Fixes

* set timeout ([#63](https://github.com/entur/gha-docker/issues/63)) ([2a93a3f](https://github.com/entur/gha-docker/commit/2a93a3f21e5bb2a5fd787bf4d656f457b48bddf9))

## [1.2.3](https://github.com/entur/gha-docker/compare/v1.2.2...v1.2.3) (2024-05-23)


### Bug Fixes

* set context ([#61](https://github.com/entur/gha-docker/issues/61)) ([e821657](https://github.com/entur/gha-docker/commit/e82165707ff7a0b90bc4a9f3f3f85f54d3a2c635))

## [1.2.2](https://github.com/entur/gha-docker/compare/v1.2.1...v1.2.2) (2024-05-22)


### Bug Fixes

* add latest tag ([#59](https://github.com/entur/gha-docker/issues/59)) ([42e27e5](https://github.com/entur/gha-docker/commit/42e27e5d12ec72f38e5af8b2f585b767b3ab59c1))

## [1.2.1](https://github.com/entur/gha-docker/compare/v1.2.0...v1.2.1) (2024-05-01)


### Bug Fixes

* meta action should point to version ([#49](https://github.com/entur/gha-docker/issues/49)) ([b54400a](https://github.com/entur/gha-docker/commit/b54400ac933911c9ddc87bf2373c3f82b7801922))

## [1.2.0](https://github.com/entur/gha-docker/compare/v1.1.3...v1.2.0) (2024-04-30)


### Features

* refactor common auth patterns ([#47](https://github.com/entur/gha-docker/issues/47)) ([fa9090a](https://github.com/entur/gha-docker/commit/fa9090af003986def8ebe36f930883a2a07cd121))

## [1.1.3](https://github.com/entur/gha-docker/compare/v1.1.2...v1.1.3) (2024-04-18)


### Bug Fixes

* add meta output ([#42](https://github.com/entur/gha-docker/issues/42)) ([23a7d6f](https://github.com/entur/gha-docker/commit/23a7d6f81d5b065a8ab5890d4262c236d9553402))
* pass along image name ([#40](https://github.com/entur/gha-docker/issues/40)) ([04498ca](https://github.com/entur/gha-docker/commit/04498cad2b4c126015a91d15b08835b9617d7cf8))

## [1.1.2](https://github.com/entur/gha-docker/compare/v1.1.1...v1.1.2) (2024-04-04)


### Bug Fixes

* multiple artifacts being uploaded instead of only img ([be278da](https://github.com/entur/gha-docker/commit/be278da7db452647f6462eea2f4914482c12a151))

## [1.1.1](https://github.com/entur/gha-docker/compare/v1.1.0...v1.1.1) (2024-04-03)


### Bug Fixes

* use cache-from for push ([#33](https://github.com/entur/gha-docker/issues/33)) ([a40ad1d](https://github.com/entur/gha-docker/commit/a40ad1d5d425a1e40339c6d265f09316f6a89518))

## [1.1.0](https://github.com/entur/gha-docker/compare/v1.0.0...v1.1.0) (2024-03-27)


### Features

* Add support for Azure Container Registry ([#28](https://github.com/entur/gha-docker/issues/28)) ([4a29710](https://github.com/entur/gha-docker/commit/4a297104553a9b283ae6e44ddabd3d1e8839839c))
* reuse build with stable API ([cc9b91b](https://github.com/entur/gha-docker/commit/cc9b91b557518b3f4cea912383188f95ccd8bc6a))

## 1.0.0 (2024-03-25)


### Features

* add reusable workflow for docker build ([#16](https://github.com/entur/gha-docker/issues/16)) ([ee8d5d8](https://github.com/entur/gha-docker/commit/ee8d5d8ec36ddbcabb93bfd105c2fac707ff621d))
* add reusable workflow for docker push ([#25](https://github.com/entur/gha-docker/issues/25)) ([e77471c](https://github.com/entur/gha-docker/commit/e77471cb3c51f6832bdcded1e2097eea2fe3e56d))


### Bug Fixes

* always tag explicit ([61b89d5](https://github.com/entur/gha-docker/commit/61b89d54707d148d04a3db799d498edd8df729dd))
* **fixture:** no dir exist uses defaults.run.working-directory ([54af60b](https://github.com/entur/gha-docker/commit/54af60bf929197a48271d3ee4798e67a2a4df51b))
* **fixture:** will fail but fail is good ([1e4ac1f](https://github.com/entur/gha-docker/commit/1e4ac1ff921ae1d024d7552b742c8d5e8aa6fa62))
* make reusable by fixing typo ([e8c2042](https://github.com/entur/gha-docker/commit/e8c2042ad02d6ec20cd216ca1faf67313f899ebe))
* mistaken property ([b239d10](https://github.com/entur/gha-docker/commit/b239d10ba8550eeaa83c4b0a331bd9e23b76975e))
* no expect fail test ([40c2506](https://github.com/entur/gha-docker/commit/40c25061b1a3194ed6d8d6d5b103f504a455470a))
* pin from tag ([41931ff](https://github.com/entur/gha-docker/commit/41931ffb3573bfa7f607c96dd442b7058f92f906))
* use always() ([647e612](https://github.com/entur/gha-docker/commit/647e612f5ed492ed8d0c03430e449ade7c1bbe91))
* use env for default and crossref ([#4](https://github.com/entur/gha-docker/issues/4)) ([78c0c63](https://github.com/entur/gha-docker/commit/78c0c63a57523eb324b0762b1eb1349725deebf3))
* use inputs ([4f0fe9c](https://github.com/entur/gha-docker/commit/4f0fe9c6fb8bad05457d6c9b2e7f8092d88b2647))
