#### Steps



    Find the feeder ID that you want to use. You can find this either as the “Site identifier” on the site page at flightaware.com/adsb/stats/user/yourusername 251, or from the PiAware logs in /var/log/piaware.log on your existing install. 
    
    The identifier looks like a series of dash-separated hex digits: 12345678-1234-1234-1234-123456789abc.

    Configure the feeder ID on the new system: piaware-config feeder-id 12345678-1234-1234-1234-123456789abc

    Restart piaware: sudo systemctl restart piaware


#### Resources

https://discussions.flightaware.com/t/how-piaware-feeders-are-identified-updated-2017-07-16/19811
