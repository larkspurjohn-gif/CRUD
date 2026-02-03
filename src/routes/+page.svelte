<script lang="ts">
  import { writable } from 'svelte/store';
  import { onMount } from 'svelte';

  // Define the interface for a record
  interface RecordType {
    id: number;
    firstName: string;
    lastName: string;
    age: number;
  }
  </script>