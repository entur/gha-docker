# Changelog

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
