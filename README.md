# DSSP - Defensec SELinux Security Policy

What started as a research project of SELinux Common Intermediate Language (CIL), and its compiler to identify their defining properties developed into a project to scratch an itch. The realization that CIL policy can be a compelling substitute for common module policy by solving existing problems, and by building on years of experience inspired the author to maintain DSSP. The project can be summarized as "back to basics", and DSSP aims to define itself by its enhanced accessibility and flexibility.

# What DSSP is and who it is for

DSSP is a SELinux security policy written in the SELinux Common Intermediate Language (CIL). CIL is designed to be used as an intermediate language that sits between the low level SELinux "kernel" language and any high level languages such as for example Reference policy. Currently there is no high level language that takes advantage of CIL.

DSSP uses CIL as a high level language because the author appreciates the design philosophy of CIL and he decided that CIL is as good as any, even if it is meant to be an intermediate language. If you want to learn more about the CIL design goals then please see the SECILC documentation [1]. Most of the arguments there also apply to DSSP.

What CIL brings to the table and what other high level languages are unable to provide in a compelling way is the ability to write complex policy. Complex policy is required to be able to write policy for complex environments suchs as graphical desktop environments.

CIL also allows DSSP to be truly modular. With module policy, policy modules are compiled individually and their compiled representations are linked together into the policy database. This makes dependency resolution impossible. Because there is no human readable policy involved at the point of linking. DSSP is modular and dependency resolution is useful because the security policy is human readable.

DSSP is designed to facilitate complex environments such as desktop environments. Processes associated with your user identity have just as much priority as processes associated with the root identity. This is unlike most common SELinux policy widely available. These SELinux security policies focus on a selection of system services only, and mostly ignore user agents.

The reason for this is that enforcing integrity in complex desktop environments is expensive, and hard without a language that enables one to write complex security policy. Even though some claim that using SELinux to enforce integrity in desktop environments is not practical, it can certainly be worth the investment.

Any alternatives such as selinux-sandbox, or XDG-app face the same challenges of dealing with complex requirements. They are still complex just in different way. Plus these technologies require additional dependencies, whereas DSSP only requires SELinux, the CIL compiler and libsepol.

DSSP is just a Git repository with human readable files, and a few shell scripts. Commands like "semanage" and "semodule" are no longer needed. Everything can be tuned by just editing or replacing files and then compiling, installing and loading the resulting policy database and configuration files.

DSSP is accessible because of this. Everything can be adjusted easily. DSSP is truly modular because it makes dependency resolution usable. DSSP can be used in any scenario because of the two aforementioned reasons, plus because it was designed with process equality in mind for the start.

Like CIL, DSSP is not designed to be user friendly, but that does not mean that it is unfriendly to users. It is designed to be flexible first and foremost, and thus useful for complex policies. DSSP just requires that you know the CIL language and the SELinux security models. It requires an initial investment. When this investment is made then DSSP actually becomes really user friendly because there are no abstractions for the sake of being "user friendly". It is very easy to maintain and configure.

If you value integrity on the desktop, if you have complex integrity requirements, or if you just want to build on a solid foundation and if you are willing to invest in learning how to effectively and efficiently use SELinux and speak CIL, then DSSP may just be what you are looking for.

DSSP shares CIL's motto: less is more.

[1] https://github.com/SELinuxProject/selinux/blob/master/secilc/docs/cil_introduction.md

### Information

Information about requirements, preparation, installation, and optimization can be found in the [DSSP Wiki](https://github.com/defensec/dssp/wiki)
