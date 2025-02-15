.. _cpm_firmware_info_module:


cpm_firmware_info -- Get firmware information from WTI OOB and PDU devices
==========================================================================

.. contents::
   :local:
   :depth: 1


Synopsis
--------

Get firmware information from WTI OOB and PDU devices






Parameters
----------

  cpm_url (True, str, None)
    This is the URL of the WTI device to send the module.


  cpm_username (True, str, None)
    This is the Username of the WTI device to send the module.


  cpm_password (True, str, None)
    This is the Password of the WTI device to send the module.


  use_https (False, bool, True)
    Designates to use an https connection or http connection.


  validate_certs (False, bool, True)
    If false, SSL certificates will not be validated. This should only be used

    on personally controlled sites using self-signed certificates.


  use_proxy (False, bool, False)
    Flag to control if the lookup will observe HTTP proxy environment variables when present.





Notes
-----

.. note::
   - Use ``groups/cpm`` in ``module_defaults`` to set common options used between CPM modules.)




Examples
--------

.. code-block:: yaml+jinja

    
    - name: Get the Firmware Information for a WTI device
      cpm_firmware_info:
        cpm_url: "nonexist.wti.com"
        cpm_username: "super"
        cpm_password: "super"
        use_https: true
        validate_certs: false

    - name: Get the Firmware Information for a WTI device
      cpm_firmware_info:
        cpm_url: "nonexist.wti.com"
        cpm_username: "super"
        cpm_password: "super"
        use_https: false
        validate_certs: false



Return Values
-------------

data (always, complex, )
  The output JSON returned from the commands sent


  firmware (success, str, 6.60)
    Current Firmware version of the WTI device.


  family (success, str, 1)
    Current family type (Console = 1  or Power = 0) of the WTI device.


  fips (success, str, 2020-02-24T20:54:03+00:00)
    If WTI device is a no FIPS only device.


  status (always, dict, {'code': '0', 'text': 'OK'})
    Return status after module completion






Status
------




- This module is not guaranteed to have a backwards compatible interface. *[preview]*


- This module is maintained by community.



Authors
~~~~~~~

- Western Telematic Inc. (@wtinetworkgear)

