# Test resources for MrBeam projects

## Setting up the test environment

- Checkout repo test_rsc ( git@github.com:mrbeam/test_rsc.git )
- Install webdriver ( https://chromedriver.chromium.org/downloads )
- Needs to be executable and in the PATH
- `pip install selenium pytest`

## Running the tests

Run  `pytest --baseurl=http://mrbeam-7537.local tests/frontend/critical_designs
- `--baseurl=http://mrbeam-7537.local`  <= specifies your beamOS url
- `--rsc_folder=../local/test_rsc/checkout` <= optional (where the root of your checkout is)

### Important files

uiUtils.py
- def load_webapp(driver, baseUrl):
- def login(driver, user="dev@mr-beam.org", pw="a"):
- def close_notifications(driver):
- def ensure_device_homed(driver):
- def add_quick_shape_*(...):
- def add_svg_url(driver, url):
- def def get_bbox(driver):
- def get_paths(driver, selector):
- def start_conversion(driver, ...):
- def select_material(driver, ...):
- def wait_for_conversion_started(driver, log_callback):
- def wait_for_ready_to_laser_dialog(driver):
- def wait_for_console_msg(driver, pattern,...):
- def cancel_job(driver):
- def cleanup_after_conversion(driver):
- def clear_working_area(driver):
- def _fill_input(driver, selector, string):
- def _click_on(driver, selector):
- def _set_checkbox(driver, selector, checked=True):
- def _set_range(driver, el, val):

frontendTestUtils.py
- def get_versions(driver):
- def compare_dimensions(bbox, exp):

gcodeUtils.py
- def get_gcode(url, local=None):
- def compare(gcode1, gcode2, ignoreComments=True, maxLines=500):

webdriverUtils.py
- def get_chrome_driver(debugTest=False):
- Def get_console_summary ()

custom_expected_conditions.py

### selenium pitfalls
- el.clear() on input[type=number]
- css transistions
- PNotify, Modals
- input[type=range] & events
- urllib3 logging
- how to catch ajax responses or events

writing more tests
- selenium ide

