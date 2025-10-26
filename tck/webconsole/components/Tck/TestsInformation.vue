<!--****************************************************************************
 * Copyright (c) 2025 Joshua "Ye" W Cox 
 *
 * All rights reserved. This program and the accompanying materials
 * are made available under the terms of the Eclipse Public License v3.0
 * which is available at https://www.eclipse.org/legal/epl-3.0/
 *
 * SPDX-License-Identifier: EPL-3.0
 *
 * Contributors:
 *    Joshua "Ye" W Cox  - initial implementation and documentation
 *    Joshua "Ye" W Cox  - updates for usability and features
 ****************************************************************************-->

<template>
  <b-sidebar
    id="Sidebar"
    :visible="showSidebar"
    @hidden="$emit('close-sidebar', false)"
    title="All Tests"
    shadow
    right
    no-close-on-route-change
    no-enforce-focus
  >
    <b-nav pills vertical v-b-scrollspy>
      <b-nav-item v-for="testName in testNames" :key="testName.name" :to="{ hash: '#' + testName.name }">
        {{ testName.readableName }}
      </b-nav-item>
    </b-nav>
  </b-sidebar>
</template>

<script>
export default {
  model: {
    prop: "showSidebar",
    event: "close-sidebar",
  },

  props: {
    /**
     * The names of tests which are shown and linked inside the sidebar.
     * @type {String[]}
     */
    testNames: {
      type: Array,
      required: true,
      default: () => [],
    },

    /**
     * Variable to show the sidebar if true.
     * @type {Boolean}
     */
    showSidebar: {
      type: Boolean,
      required: true,
      default: false,
    },
  },
};
</script>