git diff master > ~/dev/patches/temp_workaround.patch

patch -p1 < ~/dev/patches/temp_workaround.patch



* https://blog.stevenocchipinti.com/2011/09/git-diff-and-patch.html/
* https://www.shellhacks.com/git-diff-between-branches/
* https://wiki.ubuntuusers.de/patch/




----

Traceback (most recent call last):
  File "/home/lederich/dev/projects/html_cp_selenium/venv/bin/html_cp_selenium", line 11, in <module>
    load_entry_point('html-cp-selenium', 'console_scripts', 'html_cp_selenium')()
  File "/home/lederich/dev/projects/html_cp_selenium/venv/lib/python3.6/site-packages/pkg_resources/__init__.py", line 480, in load_entry_point
    return get_distribution(dist).load_entry_point(group, name)
  File "/home/lederich/dev/projects/html_cp_selenium/venv/lib/python3.6/site-packages/pkg_resources/__init__.py", line 2693, in load_entry_point
    return ep.load()
  File "/home/lederich/dev/projects/html_cp_selenium/venv/lib/python3.6/site-packages/pkg_resources/__init__.py", line 2324, in load
    return self.resolve()
  File "/home/lederich/dev/projects/html_cp_selenium/venv/lib/python3.6/site-packages/pkg_resources/__init__.py", line 2330, in resolve
    module = __import__(self.module_name, fromlist=['__name__'], level=0)
  File "/home/lederich/dev/projects/html_cp_selenium/html_cp_selenium/__init__.py", line 6, in <module>
    from . import (common, mail_actions_helper, mail_actions_receiver,
  File "/home/lederich/dev/projects/html_cp_selenium/html_cp_selenium/test_executor.py", line 5, in <module>
    from html_cp_selenium import tests
  File "/home/lederich/dev/projects/html_cp_selenium/html_cp_selenium/tests/__init__.py", line 1, in <module>
    from html_cp_selenium.tests import \
  File "/home/lederich/dev/projects/html_cp_selenium/html_cp_selenium/tests/atp.py", line 40, in <module>
    from lest.fails import soft_fail, hard_fail, track, success, info
ImportError: cannot import name 'info'

