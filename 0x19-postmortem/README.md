Issue Summary:

    Duration: 1 hour 30 minutes, 10:30 AM - 12:00 PM PST, November 15, 2023.
    Impact: Our image upload service experienced a complete outage, preventing users from uploading images to their profiles, posts, and messages. This affected approximately 80% of our active users during the peak usage period.
    Root Cause: A configuration error in our image processing service resulted in a memory leak, causing the service to crash and subsequently halting all image uploads.

Timeline:

    10:30 AM PST: Initial alert triggered by our monitoring system, indicating a spike in image upload failure rates.
    10:35 AM PST: The on-call engineer investigated the alert, observing a complete shutdown of the image processing service.
    10:45 AM PST: The engineer, assuming a server hardware issue, initiated a rolling restart of the image processing servers.
    11:00 AM PST: The restart did not resolve the issue. The engineer escalated the incident to the platform team lead.
    11:15 AM PST: The platform team lead, suspecting a configuration problem, reviewed recent changes and discovered a faulty configuration update that introduced a memory leak.
    11:30 AM PST: The team rolled back the faulty configuration update.
    12:00 PM PST: Image upload service restored.

Root Cause and Resolution:

The root cause of the outage was a configuration error in our image processing service. A recent update to the service introduced a faulty configuration setting that caused a memory leak. This leak gradually consumed all available memory, eventually leading to the service crashing and halting all image uploads.

The resolution involved rolling back the faulty configuration update. This restored the service to its previous, stable state, allowing image uploads to resume.

Corrective and Preventative Measures:

To prevent similar incidents in the future, we will implement the following measures:

    Improved Configuration Management: We will implement stricter testing procedures for all configuration updates, including automated testing and manual review by a second engineer.
    Enhanced Monitoring: We will expand our monitoring system to include more granular metrics related to memory usage and resource consumption within the image processing service.
    Memory Leak Detection Tools: We will integrate automated memory leak detection tools into our development workflow to identify and address memory issues early in the development cycle.

