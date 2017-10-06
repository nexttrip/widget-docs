```html
<script>
  !function(t,e,n,o){var a,i,r=t.location;t["NextTripBookingRef"]=o,t[o]=t[o]||function(){(t[o].q=t[o].q||[])
  .push(arguments)},t[o].s=r.origin||r.protocol+"//"+r.hostname,a=e.createElement("script"),
  i=e.getElementsByTagName("script")[0],a.async=1,a.src=n+"?"+(new Date).getTime(),
  i.parentNode.insertBefore(a,i),[].forEach.call(e.querySelectorAll("[data-nexttrip]"),
  function(e){e.addEventListener("click",function(e){t[o]("dataset",e.target.dataset),e.preventDefault()})})}
  (window,document,"https://next-trip-booking.now.sh/booking.js","nextTrip");

  nextTrip.customerId = 'TSIMANE'
  nextTrip.dealId = 'TSIMANE'
  nextTrip.productId = 'PLUMAWEEKLY2017'
  
  nextTrip.lang = 'es'  // el lenguaje que debe utilizar el widget

</script>
```
