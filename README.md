# moodlepy

[![PyPi Package Version](https://img.shields.io/pypi/v/moodlepy)](https://pypi.org/project/moodlepy/)
[![Supported Python versions](https://img.shields.io/pypi/pyversions/moodlepy)](https://pypi.org/project/moodlepy/)
[![LICENSE](https://img.shields.io/github/license/hexatester/moodlepy)](https://github.com/hexatester/moodlepy/blob/master/LICENSE)
[![Tests](https://github.com/hexatester/moodlepy/workflows/Tests/badge.svg)](https://github.com/hexatester/moodlepy/actions?query=workflow%3ATests)
[![codecov](https://codecov.io/gh/hexatester/moodlepy/branch/master/graph/badge.svg)](https://codecov.io/gh/hexatester/moodlepy)
[![pre-commit](https://img.shields.io/badge/pre--commit-enabled-brightgreen?logo=pre-commit&logoColor=white)](https://github.com/pre-commit/pre-commit)
[![Mypy](https://img.shields.io/badge/Mypy-enabled-brightgreen)](https://github.com/python/mypy)

Python wrapper for moodle web service.

## Introduction

This library provide a pure Python interface for [Moodle Web Service](https://docs.moodle.org/dev/Web_services). It's compatible with Python versions 3.7+

> Install moodlepy==0.22.2 for python 3.6 support.

## Installing

You can install or upgrade moodlepy with:

```bash
pip install moodlepy --upgrade
```

Or you can install from source with:

```bash
git clone https://github.com/hexatester/moodlepy
cd moodlepy
python setup.py install
```

## Usage

Example usage

```python
from moodle import Moodle
url = 'https://my.domain/webservice/rest/server.php'
token = 'super secret token'
moodle = Moodle(url, token)
dict_site_info = moodle('core_webservice_get_site_info')
site_info = moodle.core.webservice.get_site_info()  # return typed site_info

print(dict_site_info)
print(site_info)

# or
from moodle import Mdl
from moodle.core.webservice import BaseWebservice

moodle = Mdl(url, token)
webservice = BaseWebservice(moodle)
site_info2 = webservice.get_site_info()

assert site_info == site_info2
```

❗️ If the function area does not have a type in the [support table](#moodle-web-service-support), the return value is in accordance with the [Moodle web service documentation](https://sandbox.moodledemo.net/admin/webservice/documentation.php), wich mostly dict.

In the future all of [Web service functions](https://docs.moodle.org/dev/Web_service_API_functions) will be covered by moodlepy.

# Moodle Web Service support

| Area                 | Functions | Types | Tests | Status |
| -------------------- | --------- | ----- | ----- | ------ |
| auth_email           | A         | A     |       |        |
| block                | A         | A     |       |        |
| core_auth            | A         | A     |       |        |
| core_backup          | A         | A     |       |        |
| core_badge           | A         | A     | A     |        |
| core_blog            | A         | A     | A     |        |
| core_calendar        | A         | A     |       |        |
| core_cohort          | A         | A     |       |        |
| core_comment         | A         | A     |       |        |
| core_competency      |           |       |       |        |
| core_completion      | A         | A     |       |        |
| core_course          |           |       |       |        |
| core_customfield     | A         | A     |       |        |
| core_enrol           |           |       |       |        |
| core_fetch           |           |       |       |        |
| core_files           |           |       |       |        |
| core_filters         |           |       |       |        |
| core_form            |           |       |       |        |
| core_get             |           |       |       |        |
| core_grades          | A         |       |       |        |
| core_grading         |           |       |       |        |
| core_group           |           |       |       |        |
| core_h5p             |           |       |       |        |
| core_message         | A         |       |       |        |
| core_notes           | A         | A     |       |        |
| core_output          |           |       |       |        |
| core_question        |           |       |       |        |
| core_rating          |           |       |       |        |
| core_role            |           |       |       |        |
| core_search          |           |       |       |        |
| core_session         |           |       |       |        |
| core_tag             |           |       |       |        |
| core_update          |           |       |       |        |
| core_user            |           |       |       |        |
| core_webservice      | A         | A     | A     | A      |
| enrol_guest          | A         | A     |       |        |
| enrol_manual         | A         | A     |       |        |
| enrol_self           | A         | A     |       |        |
| gradereport_overview |           |       |       |        |
| gradereport_user     |           |       |       |        |
| gradingform_guide    |           |       |       |        |
| gradingform_rubric   |           |       |       |        |
| local_mobile         |           |       |       |        |
| message_airnotifier  |           |       |       |        |
| message_popup        |           |       |       |        |
| mod_assign           |           |       |       |        |
| mod_book             |           |       |       |        |
| mod_chat             | A         |       |       |        |
| mod_choice           |           |       |       |        |
| mod_data             | A         |       |       |        |
| mod_feedback         |           |       |       |        |
| mod_folder           | A         | A     |       |        |
| mod_forum            |           |       |       |        |
| mod_glossary         |           |       |       |        |
| mod_imscp            |           |       |       |        |
| mod_label            |           |       |       |        |
| mod_lesson           |           |       |       |        |
| mod_lti              |           |       |       |        |
| mod_page             | A         | A     |       |        |
| mod_quiz             |           |       |       |        |
| mod_resource         | A         | A     |       |        |
| mod_scorm            |           |       |       |        |
| mod_survey           |           |       |       |        |
| mod_url              | A         | A     |       |        |
| mod_wiki             |           |       |       |        |
| mod_workshop         | A         |       |       |        |
| report_competency    |           |       |       |        |
| report_insights      |           |       |       |        |
| tool_analytics       |           |       |       |        |
| tool_lp              |           |       |       |        |
| tool_mobile          | A         | A     |       |        |
| tool_templatelibrary |           |       |       |        |
| tool_usertours       |           |       |       |        |
| tool_xmldb           |           |       |       |        |
