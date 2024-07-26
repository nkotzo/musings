# The Farm:  "Cattle, not pets"
Pets vs. cattle is an analogy that started hitting common vernacular at least for me in the mid-2010s, you’ll find hundreds of 
developer memes with a simple Google search.  It’s an analogy to help you think about and deal with server infrastructure
that encompasses the critical ideas of automation, orchestration, and flexibility.

If an organization is to realize operational efficiencies, availability qualities, and deployments at speed,
it needs to eliminate its tendency to rely on large, monolithic, and likely, unique system deployments.  
This strategy will likely force technology leaders to go against organizational momentum, possibly their instincts, 
and cultural norms.  However, if they can overcome that, the organization can enjoy the increased security and flexibility
of modern cloud infrastructures. 

## A Bit of History
The best I can tell a Microsoft engineer, Bill Baker, used it during a discussion about SQL deployments to explain how server 
treatment changed over time while discussing scale-up v scale-out infrastructure deployments. 

![Thank you Copado for PetsVCattle image](/images/PetsVCattle.jpg)

While the treatment of pets sounds more positive, it’s the cattle approach developers need to target, the automation
of scale-out architectures.   In the early days of cloud deployments, it was mostly about infrastructure, but adapting
to modern agile processes its a requirement for DevOps, DevSecOps, Platform Engineering, etc. that are driving todays
feature deployments.   That’s not to say the cattle approach will work all the time, there are exceptions to every rule.
But they should be exceptions, and, not the rule.  “Not everything is disposable, and when an asset isn’t, it requires
pet treatment. The goal is to minimize the number of pets and maximize cattle to create an easy to protect and manage
infrastructure.”

## Extending the farm, Additions to the “Cattle, not Pets” Analogy
What about Containers?   In a [Bernard Golden post](https://thenewstack.io/pets-and-cattle-symbolize-servers-so-what-does-that-make-containers-chickens/) 
he used chickens to describe container environment.  “Chickens grow to maturity much faster than cattle — six weeks for
a chicken compared to around 24 months for cattle. They’re more efficient than cattle in terms of resource use — a chicken
only takes 1.7 pounds of food to add a pound of mass, while a steer requires over three pounds”

He goes on to describe the analogy further, “This greater efficiency of chickens compared to cattle is exactly mirrored
by containers vis a vis virtual machines. Containers launch in seconds, rather than the minutes more typical of virtual
machines. Containers require far fewer compute resources in comparison to virtual machines.”

There’s also a speed element involved. Physical servers take the longest amount of time to provision and configure, followed
by VMs (with appropriate automation in place) and then Containers. The closer you move to a well-architected container model,
the faster it is to remove, replace or patch one of the components when necessary.  All of this comes together with providers
like Azure, Amazon and Google to enable us to scale rapidly in both directions (up and down) to meet the demands of the customers.

Keeping in line with the animal theme, [Eric Johnson wrote a blog](https://blog.rackspace.com/pets-cattle-and-nowinsects) post for 
RackSpace which introduced insects. This term was introduced to describe serverless and Functions as a Service.
As you’d expect, insects have a much lower life expectancy than chickens; in fact, some insects only have a lifespan of a
few hours. Fitting in well with serverless and Functions as a Service as these have a lifespan of seconds.

The farm or animal analogy starts to break down with [Marin Fowler’s post](https://martinfowler.com/bliki/SnowflakeServer.html) about
Snowflakes representing highly delicate, detailed server deployments.  But hopefully you get the point. 

## Putting Cattle, not Pets to Practical Use
The practical application of pets vs. cattle vs. chickens vs insects centers on minimizing the systems which require individual
or special attention. Automation is necessary, as the sheer number of cattle, chicken or insects is unsustainable without it. 

At first glance, immutable infrastructure—which cannot be changed—seems counterintuitive to the cattle approach.  If you can’t
change or update a server the server naturally becomes disposable.   If there’s something wrong with it, it’s not reconfigured
or patched. It’s replaced with a new server built from a standard image, with necessary changes incorporated.

Patches and updates are an unavoidable reality, they ensure the ongoing security and compliance of the infrastructure.  In the
good old days, operation teams would apply these patches or upgrades in-place, often in a non-consistent fashion, which can
result in the servers drifting further away from ‘good’.   Immutable systems move this responsibility to the image creation
process, and optimize for replacing the running image quickly, reducing the scope of change to a single, well defined and well
tested image that can be deployed repeatedly, and often without interruption to ongoing operations. These systems and processes
also cut configuration drift.  When systems drift from a known ‘good’ changes aren’t mapped effectively, making reproduction
(or restoration) into a backup or secondary source near impossible.

So how do we get to, and, manage immutable systems.  Infrastructure as code is a crucial component of building these immutable
systems.  Establishing the IaC code base builds a foundation that helps deliver these rapidly configured, immutable, replacement
servers.  By leveraging software development best practices, where changes are visible within the code itself, while pull
requests and peer reviews help drive quality throughout the process.   Reducing your dependence on excessive or dated 
documentation.

Container orchestration is another vital component of the farm environment, as microservice architectures require the
deployment of granular level services. This process allows teams to automate tasks related to provisioning and deploying
containers, allocating resources between them, and monitoring their health.  I’m going to leave this topic here as discussing
topics like helm can take us on yet another journey.  

Essentially, the cattle v pets v chickens v insects philosophy minimizes infrastructure changes, breaks programs down to their
smallest possible components, and leverages automation to control all these moving parts. The result is an infrastructure that
is scalable, secure, and flexible.
