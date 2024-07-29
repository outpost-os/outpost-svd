# SPDX-License-Identifier: Apache-2.0
#
# Copyright 2023 Ledger SAS
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
# http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.


irq_defs_in = files('irq_defs.h.in')
layout_in = files('layout.h.in')
peripheral_defs_in = files('peripheral_defs.h.in')

# Usage exemple:
#
#  - with custom target(s)
#
# irq_def_h = custom_target('gen_irq_defs',
#     input: irq_defs_in,
#     output: '@BASENAME@',
#     depends: [ svd_json ],
#     command: [ jinja_cli, '-d', svd_json, '-o', '@OUTPUT@', '@INPUT@' ],
# )
#
# layout_h = custom_target('gen_layout',
#     input: layout_in,
#     output: '@BASENAME@',
#     depends: [ svd_json ],
#     command: [ jinja_cli, '-d', svd_json, '-o', '@OUTPUT@', '@INPUT@' ],
# )
#
#  - with generator:
#  jinja_gen = generator(jinja_cli,
#       output: '@BASENAME@',
#       arguments: ['-d', '@0@'.format(svd_json),
#                   '-o', '@OUTPUT@',
#                   '@EXTRA_ARGS@',
#                   '@INPUT@'],
#       depends: [ svd_json ])
#
# irq_def_h = jinja_gen.process(irq_defs_in)
# layout_h = jinja_gen.process(layout_in)
#
# `NAME` value must be either a peripheral `name` **or** peripherals `groupName`
# gpio_h = jinja_gen.process(peripheral_defs_in, extra_args: ['--define', 'NAME', 'GPIO'])
