<!-- http://codematic.net/excel-development/excel-vba/excel-vba-Security.htm -->

# VBA Security Trade-offs

There are two main aspects to security

Potential loss of intellectual property if people access source code without permission.

Potential danger from a malicious user subverting the expected behaviour for their own (possibly disastrous) purposes.

VBA security has for years revolved around security through obscurity. Any security revolved around the fact that the underlying file format was not officially documented. The VBA is not encrypted or scrambled, or otherwise protected. There is simply a flag in the file that says should Excel ask for a password before displaying the VBA. That means other file readers apart form Excel are free to respect or ignore that setting. After that the actual code is pretty much a bunch of embedded text files.

In recent times VBA file structure documentation has been published to assist interoperability, so it is even easier now for people to inspect the internals of workbooks and add-ins.

VBA security is fairly poor, the code is not compiled, and the source is available in the excel file. The password protection is pretty easy to circumvent. This reflects Excel/VBA target as an end user application. Code security can be enhanced by moving to COM components or compiled code such as C, if there is a real need.

Our experience is that although initially clients often seek the additional intellectual property protection of something other than VBA, once they realise the cost in complexity, schedule and finance, they frequently accept VBA as the best compromise. We are always happy to quote to convert VBA system to other technologies.

The danger of having code subverted is real enough, although we don't often hear of actual incidents. The simplest solution is to sign the VBA project, any subsequent modification will then trigger a warning. Sadly code signing is still not that common so unsigned code does not worry users. Lucky then that most VBA is maintained within the organisations firewall.
