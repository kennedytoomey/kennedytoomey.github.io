---
title: "Applying Football's Defense in Depth Principles to Application Security "
date: 2025-09-04 12:00:00 -0400  
description: Breaking down football to teach application security concepts.  
tags: ['conference_talk_recap', 'application_security_basics']
---
# Introduction 

I’ve been watching football for as long as I can remember. For me, it has always been about more than just the sport. It meant family bonding time, great food, a way to bring the community together, and in college, it was simply a way of life.

Before I get too deep into the football talk, here are a few quick disclaimers:

* You don’t need any prior knowledge of football or application security to follow along.  
* This post is about American football, not soccer. Soccer fans, you might need to use a bit of imagination.  
* Some of the comparisons in this post are a little creative and not always perfect. I’ve done my best, but keep your imagination open.

This post is a follow up of a talk that I gave at SCaLE 22x. If you’d like to check it out, you can find the  recording and all associated resources [here](https://github.com/kennedytoomey/scale22x). 

# Defense in depth 

Defense in depth is the idea that if you have one control and it fails you are in trouble, but if you have multiple layers of protection, one can fail without everything falling apart. 

Think about when you are driving a car. You wear a seatbelt. There are also airbags deploy in the event of a crash. Manufacturers design cars with crumple zones to absorb the impact of a collision and minimize injury. They also have anti-lock braking systems to help maintain control while stopping. Newer models even come with lane departure warning systems and automatic emergency breaking. Each of these features is helpful on its own, but the real strength comes from using them together. They work in combination to give you the best possible chance of arriving safely at your destination.

Cybersecurity works in a similar way. We want to layer our defenses. If one control misses something, another might catch it. The goal is to reduce the overall risk and make it harder for an attacker to succeed.

# The basics 

Before we dive deeper, I want to quickly cover the basics of football. I’ll go into more detail later, but here’s the high-level view. The offense starts with the ball. Their job is to move it down the field and score. The defense’s goal is to stop them from doing that. That’s the most simplified version of the game, but if you want a bit more context, watch this [one-minute video](https://www.youtube.com/watch?v=3t6hM5tRlfA) that breaks it down in more detail. 

You might be wondering, why use football to explain a security concept? My hope is that by connecting application security to a familiar sport, the ideas become more relatable and easier to understand. Also, if I’m being honest, I tend to connect everything back to football.

This post focuses on application security (AppSec) topics, but you can apply the core idea of defense in depth across all security disciplines. I’ve written this with the assumption that most readers have limited experience with application security and are likely developers or work closely with them. No matter your role, my goal is that you walk away with a better understanding of key AppSec concepts.

# The coaching staff

In my mind, the coaching staff is the equivalent of the security team. Depending on the situation, you might be a part of a large security department or you might be the entire team. 

### The head coach \= The CISO

The head coach is responsible for setting the overall game strategy. They call the shots and carry the burden of the team’s success or failure. In the security world, this is the Chief Information Security Officer (CISO). The CISO sets the organization's security vision and direction, balancing priorities like risk, business needs, and resources. In both roles, success depends on collaboration. While they make the final call, head coaches and CISOs rely on trusted advisors to guide them toward smart, strategic decisions.

### The defensive coordinator \= The security architect or engineer

The defensive coordinator is in charge of designing and leading the defensive strategy. They develop plays, work with the team to execute them, and adjust tactics as needed. This maps closely to the work of Security Architects and Engineers. These folks take the high-level strategy and turn it into something actionable. They build systems, design controls, and work hand-in-hand with the CISO to make sure the game plan comes to life. Like defensive coordinators, they also have advisors and collaborators who bring even more specialized expertise to the table.

### Position coaches \= Security SMEs

Position coaches are the experts that focus on developing specific skills. This could be a quarterback coach or a kicking coach that helps individual players refine their skills in very focused areas. When it comes to their specialty, they bring deep knowledge, but they are not able to help in every area of the game.This is similar to subject matter experts (SMEs) in security. Whether it’s someone who specializes in Azure AD, threat modeling, or cloud infrastructure, SMEs bring focused expertise. They may not cover every part of the security landscape in depth, but in their domain, they serve as the go-to person.

## Behind the scenes

With any good team, work is done behind the scenes to support success. Preparation, planning, and analysis often matter just as much as what happens on the field.

### Playbooks \= Incident response playbooks

Football teams rely on playbooks for both offense and defense. These playbooks contain a collection of potential plays that teams can use depending on the situation. In security, we have something similar in the form of incident response playbooks. These are sets of documented procedures that outline how to respond to specific types of security incidents. Just like in football, the goal is to be ready to act quickly and effectively when something goes wrong.

### Watching film \= Threat modeling

Another behind-the-scenes activity in football is watching film. Players and coaches study past games to learn more about their own performance and their opponents. They look for weak spots, patterns, and areas for improvement. The coaching staff then builds a plan to fix their own issues and take advantage of the opposition’s vulnerabilities. This is very similar to threat modeling in application security. Threat modeling helps identify weak points in an application or system before an attacker does. From there, the team can develop and apply strategies to strengthen those areas. 

# The offense

When we think about the offense, we are really thinking about the attack. In football, the offense’s goal is to break through the defense and score. In security, it is not all that different. An attacker’s goal is to bypass your defenses, and their motivations can vary from stealing data to trying to gain a foothold in your systems. 

### Quarterback \= Threat actor

When most people think of a football offense, the first position that comes to mind is the quarterback. Quarterbacks are often the most well-known players because every play starts with them. They lead the offense, call the plays, and execute the plan. In the context of security, I think of the quarterback as the equivalent of the threat actor. This person or group organizes and coordinates the attack, deciding when and how to move forward. In both cases, they are the ones orchestrating the strategy and keeping the offense in motion.

### Skill positions \= Tools & scripts

Then there are the skill positions, like wide receivers and running backs. These players are responsible for gaining yards and finding weaknesses in the defense. They run, catch, and slip through defenders, all in an effort to move the ball down the field and eventually score. In security, these positions remind me of the tools and scripts that attackers use. Just like a receiver looks for gaps in coverage, these tools look for vulnerabilities in your system. Once they find a weak spot, they can exploit it to gain access and move deeper into the environment.

The defense

In football, the defense consists of three distinct layers: the defensive line, the linebackers, and the secondary. Each layer plays a unique role, and together, they form a complete and resilient defense which is something we hope to emulate in our application security strategy.

## The defensive line

The first layer of defense in football is the defensive line. These players are responsible for stopping the play before it ever gets going by putting pressure on the quarterback and disrupting running plays. In application security, this shift-left mindset maps well to a set of tools focused on identifying vulnerabilities as soon as possible in the software development lifecycle (SDLC).

### Defensive tackles \= SAST

The defensive tackle’s purpose is to stop plays early. They do this by pressuring the quarterback and disrupting run plays in the middle of the field. This role shares similarities with Static Application Security Testing (SAST). SAST scans analyze the source code, usually early in the software development lifecycle. These scans can help identify insecure code patterns before deploying the application. However, because they do not have full runtime context, they tend to produce more false positives.

### Defensive ends \= IAST

On the edges of the line, we have the defensive ends. They share a similar objective with the tackles but approach it from a different angle. Their focus is on protecting the outer edges and containing plays that try to escape the middle. This maps well to Interactive Application Security Testing (IAST). IAST tools also look for vulnerabilities in the source code, but they do so while the application is running. Because they operate at runtime, they benefit from greater context and typically generate more accurate results. IAST is often used later in the SDLC, once the application is running.

### Nose tackle \= SCA

Finally, we have the nose tackle, a specialized position that lines up directly across from the offense’s center. Like the rest of the line, the nose tackle is focused on disrupting plays from the start, especially in the center of the field. This position is comparable to Software Composition Analysis (SCA), which focuses on identifying vulnerabilities in third-party libraries and dependencies. SCA scans should be run regularly, even if no code has changed, because new vulnerabilities may surface in packages you already use. 

## The linebackers

Most people consider linebackers to be the most versatile players on the field. Positioned just behind the defensive line, they serve as a flexible layer of defense, able to adapt to both running and passing plays. There are two types of linebackers: outside and inside. Each plays a critical role in protecting gaps and supporting the overall defensive strategy.

### Outside linebackers \= DAST

Outside linebackers are responsible for covering the edges and filling in any gaps that the defensive line misses. They still aim to pressure the quarterback, but they also defend against both run and pass plays that slip past the defensive line. In the application security world, this role aligns with Dynamic Application Security Testing (DAST). DAST tools run automated attacks against a running application in order to detect vulnerabilities in real time. They are especially effective at catching issues like cross-site scripting (XSS), missing security headers, and other easily testable flaws. The main limitation is that they operate without full knowledge of the application’s internals, which means they can miss more complex logic issues. 

### Inside linebackers \= Penetration testing

Inside linebackers are the ultimate jack of all trades. They can pressure the quarterback, stop the run, drop into pass coverage, and adjust on the fly. These players often act as on-field leaders, helping to coordinate the entire defense. This maps closely to penetration testing, or pentests. Pentests are customized security assessments that simulate real-world attacks against a running application. They can be manual, automated, or a combination of both, and are tailored to the specifics of the application to uncover more complex and subtle vulnerabilities. Penetration tests tend to produce highly accurate and impactful results, but they come with tradeoffs. They are typically time-consuming, expensive, and difficult to perform on a frequent basis. This is why many teams use tools like DAST as a supplement, running pentests periodically to dig deeper when it matters most.

## The secondary

Now it’s time to talk about the last line of defense: the secondary. By the time these players step in, a big play has either already happened or is about to happen. Even if a wide receiver catches the ball for a large gain, the play hasn’t ended. There is still a chance to stop the player before they score. In security terms, this is where risk mitigation comes into play, even if earlier layers of defense have failed.

### Cornerbacks \= WAF

Cornerbacks are responsible for covering the short and intermediate areas of the field. Their job is to prevent short passes, contain breakthrough runs, and respond quickly to anything that slips past the first two layers. This aligns well with a Web Application Firewall (WAF). A WAF sits at the edge of the application, monitoring and filtering incoming traffic to block known malicious requests. WAFs provide solid visibility into attack patterns and can also help protect against Distributed Denial of Service (DDoS) attacks by identifying and mitigating high volumes of suspicious traffic. However, WAFs are limited by their position. Since they operate outside of the application, they do not have access to its internal context. This means they may struggle to prevent sophisticated or deeply embedded exploits.

### Safeties \= RASP

Safeties are the true last line of defense. Their job is to protect the deep part of the field, break up long passes, and bring down the ball carrier if all else fails. They are the players who step in when everything else has gone wrong. In application security, this role is similar to Runtime Application Self-Protection (RASP). RASP tools run within the application itself, giving them the ability to understand its internal logic and behavior. Because they operate from inside, they can detect and prevent exploits based on real-time application context from traces. When a request triggers a known malicious pattern, RASPs can block the attack before it succeeds. RASPs excel at exploit prevention. However, it is not designed for large-scale traffic filtering, so it does not help with DDoS protection. 

# Teamwork makes the dream work

No single position can cover the entire field, and the same goes for application security. No one tool can protect against every type of attack.

Imagine sending only the defensive line out onto the field. They would be completely ineffective at covering deep passes, because the secondary covers that area. In the same way, relying on a single AppSec tool leaves gaps in coverage where other tools are better suited to respond.

That said, not every player affects every play. All eleven players are on the field, but depending on what the offense runs, some may have a bigger impact than others. This mirrors how security tools work. You don’t need each tool for every request, but you still want them in place. That way, when you need them, they are ready to alert.

This is the heart of defense in depth. A single preventive measure might fail. That is why we implement multiple layers of protection and defense, each designed to catch what the others might miss. Every layer brings a unique strength to the overall defense, and when they work together, they give your application the best possible shot at staying secure.
