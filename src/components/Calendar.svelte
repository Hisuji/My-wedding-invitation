<script>
  import moment from "moment";

  export let flowerSrc;

  let calendarSrc = "images/calendar.png";
  let dDay = moment("2022-03-19");
  let today = moment().startOf("day");
  let diff = today.diff(dDay, "days");
  console.log(today);
</script>

<style>
  /* your styles go here */
</style>

<!-- markup (zero or more items) goes here -->
<div class="flex justify-center mt-20">
  <img src="{flowerSrc}" alt="flower" class="w-8" />
</div>
<div class="text-center">
  <p class="text-xs mb-8 tracking-widest">결혼합니다</p>
</div>
<div class="flex justify-center">
  <img src="{calendarSrc}" alt="calendar" />
</div>
<div class="text-center">
  <p>
    <span class="text-sm text-red-500 font-semibold mr-2">D-day</span>
    {#if dDay > today}
      예식일이 {Math.abs(diff)}일 남았습니다.
    {:else}
      예식일이 {Math.abs(diff)}일 지났습니다.
    {/if}
  </p>
</div>
