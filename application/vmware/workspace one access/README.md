
### CVE-2022-31700 post-auth RCE

Java Bean Validation 的实战利用，之前对这种洞的理解还停留在单一 sink `ConstraintValidatorContext.buildConstraintViolationWithTemplate()` 上，没有考虑到
应用自定义 Bean Validator 的情况。

漏洞分析
- https://trenchant.io/vmware-workspace-one-access/ 


