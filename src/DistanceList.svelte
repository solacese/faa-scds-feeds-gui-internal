<script>
  import { distanceStatsCache } from "./stores";
  import VirtualList from "@sveltejs/svelte-virtual-list";
  import DistanceListItem from "./DistanceListItem.svelte";

  let dummyArray = [
    { id: "SWA", distance: 82739.707875192762 },
    { id: "AAL", distance: 75246.193329843256 },
    { id: "DAL", distance: 45041.926220355119 },
    { id: "UAL", distance: 29202.606273851223 },
    { id: "JBU", distance: 18581.967440776476 },
  ];
</script>

<VirtualList
  items={$distanceStatsCache.sort((a, b) => {
    a.distance - b.distance;
  })}
  let:item>
  <DistanceListItem {...item} />
</VirtualList>
