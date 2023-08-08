# Installing Microsoft TrueType Fonts on Linux with/without internet

## Online Installation

1) Install the following packages:

'''
yum install rpm-build
yum install ttmkfdir
yum install xfs
yum install chkfontpath
'''

2) Install CABExtract tool

'''
yum install cabextract
'''

If above fails, you may download the rpm package and install it

'''
wget https://dl.fedoraproject.org/pub/epel/8/Everything/x86_64/Packages/c/cabextract-1.9-7.el8.x86_64.rpm
yum install cabextract-1.9-7.el8.x86_64.rpm
'''

3) Install MSTTCoreFonts:

'''
wget http://corefonts.sourceforge.net/msttcorefonts-2.5-1.spec
rpmbuild -ba msttcorefonts-2.5-1.spec
'''

If above rpmbuild command is successful it writes few lines before the end the messages similar to:

Example	
Copy Code
Wrote: /usr/src/redhat/SRPMS/msttcorefonts-2.5-1.src.rpm
Wrote: /usr/src/redhat/RPMS/noarch/msttcorefonts-2.5-1.noarch.rpm
Check for the path where msttcorefonts-2.5-1.noarch.rpm is located as the result of rpmbuild command above. Use that path in the next command:

'''
yum localinstall --nogpgcheck /usr/src/redhat/RPMS/noarch/msttcorefonts-2.5-1.noarch.rpm
'''
