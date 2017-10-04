```javascript
!function(t,e,n,a){var o,i;t["NextTripBookingRef"]=a,t[a]=t[a]||function(){(t[a].q=t[a].q||[]).push(arguments)},t[a].s=t.location.origin,o=e.createElement("script"),i=e.getElementsByTagName("script")[0],o.async=1,o.src=n,i.parentNode.insertBefore(o,i),
[].forEach.call(e.querySelectorAll("[data-nexttrip]"),function(e){e.addEventListener("click",function(e){t[a]("dataset",e.target.dataset),e.preventDefault()})})
}(window,document,"https://next-trip-booking.now.sh","nextTrip");
```
