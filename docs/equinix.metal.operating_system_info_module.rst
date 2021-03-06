.. _equinix.metal.operating_system_info_module:


***********************************
equinix.metal.operating_system_info
***********************************

**Gather information about Equinix Metal operating_systems**


Version added: 1.4.0

.. contents::
   :local:
   :depth: 1


Synopsis
--------
- Gather information about Equinix Metal operating_systems.
- API is documented at https://metal.equinix.com/developers/api/operating_systems/.



Requirements
------------
The below requirements are needed on the host that executes this module.

- packet-python >= 1.43.1


Parameters
----------

.. raw:: html

    <table  border=0 cellpadding=0 class="documentation-table">
        <tr>
            <th colspan="1">Parameter</th>
            <th>Choices/<font color="blue">Defaults</font></th>
            <th width="100%">Comments</th>
        </tr>
            <tr>
                <td colspan="1">
                    <div class="ansibleOptionAnchor" id="parameter-"></div>
                    <b>api_token</b>
                    <a class="ansibleOptionLink" href="#parameter-" title="Permalink to this option"></a>
                    <div style="font-size: small">
                        <span style="color: purple">string</span>
                         / <span style="color: red">required</span>
                    </div>
                </td>
                <td>
                </td>
                <td>
                        <div>The Equinix Metal API token to use</div>
                        <div>If not set, then the value of the METAL_API_TOKEN, PACKET_API_TOKEN, or PACKET_TOKEN environment variable is used.</div>
                        <div style="font-size: small; color: darkgreen"><br/>aliases: auth_token</div>
                </td>
            </tr>
            <tr>
                <td colspan="1">
                    <div class="ansibleOptionAnchor" id="parameter-"></div>
                    <b>distros</b>
                    <a class="ansibleOptionLink" href="#parameter-" title="Permalink to this option"></a>
                    <div style="font-size: small">
                        <span style="color: purple">list</span>
                         / <span style="color: purple">elements=string</span>
                    </div>
                </td>
                <td>
                </td>
                <td>
                        <div>One or more operating_system distros.</div>
                </td>
            </tr>
            <tr>
                <td colspan="1">
                    <div class="ansibleOptionAnchor" id="parameter-"></div>
                    <b>slugs</b>
                    <a class="ansibleOptionLink" href="#parameter-" title="Permalink to this option"></a>
                    <div style="font-size: small">
                        <span style="color: purple">list</span>
                         / <span style="color: purple">elements=string</span>
                    </div>
                </td>
                <td>
                </td>
                <td>
                        <div>One or more operating_system slugs.</div>
                </td>
            </tr>
    </table>
    <br/>




Examples
--------

.. code-block:: yaml

    # All the examples assume that you have your Equinix Metal API token in env var METAL_API_TOKEN.
    # You can also pass it to the api_token parameter of the module instead.

    - name: Gather information about all operating_systems
      hosts: localhost
      tasks:
        - equinix.metal.operating_system_info:


    - name: Gather information about a particular operating_system using slug
      hosts: localhost
      tasks:
        - equinix.metal.operating_system_info:
          slugs:
            - ubuntu_20_10



Return Values
-------------
Common return values are documented `here <https://docs.ansible.com/ansible/latest/reference_appendices/common_return_values.html#common-return-values>`_, the following are the fields unique to this module:

.. raw:: html

    <table border=0 cellpadding=0 class="documentation-table">
        <tr>
            <th colspan="1">Key</th>
            <th>Returned</th>
            <th width="100%">Description</th>
        </tr>
            <tr>
                <td colspan="1">
                    <div class="ansibleOptionAnchor" id="return-"></div>
                    <b>operating_systems</b>
                    <a class="ansibleOptionLink" href="#return-" title="Permalink to this return value"></a>
                    <div style="font-size: small">
                      <span style="color: purple">list</span>
                    </div>
                </td>
                <td>always</td>
                <td>
                            <div>Information about each operating_system that was found</div>
                    <br/>
                        <div style="font-size: smaller"><b>Sample:</b></div>
                        <div style="font-size: smaller; color: blue; word-wrap: break-word; word-break: break-all;">[{ &quot;distro&quot;: &quot;ubuntu&quot;, &quot;name&quot;: &quot;Ubuntu 20.10&quot;, &quot;provisionable_on&quot;: [ &quot;c1.small.x86&quot;, &quot;baremetal_1&quot;, &quot;c2.medium.x86&quot;, &quot;c3.medium.x86&quot;, &quot;c3.small.x86&quot;, &quot;g2.large.x86&quot;, &quot;m1.xlarge.x86&quot;, &quot;baremetal_2&quot;, &quot;m2.xlarge.x86&quot;, &quot;m3.large.x86&quot;, &quot;n2.xlarge.x86&quot;, &quot;s1.large.x86&quot;, &quot;baremetal_s&quot;, &quot;s3.xlarge.x86&quot;, &quot;t1.small.x86&quot;, &quot;baremetal_0&quot;, &quot;x1.small.x86&quot;, &quot;baremetal_1e&quot;, &quot;x2.xlarge.x86&quot;, &quot;x3.xlarge.x86&quot; ], &quot;slug&quot;: &quot;ubuntu_20_10&quot;, &quot;version&quot;: &quot;20.10&quot; }]</div>
                </td>
            </tr>
    </table>
    <br/><br/>


Status
------


Authors
~~~~~~~

- Jason DeTiberus (@detiber) <jdetiberus@equinix.com>
