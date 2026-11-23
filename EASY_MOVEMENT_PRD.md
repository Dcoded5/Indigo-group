# Easy Movement: Product Requirements Document

**Product name:** Easy Movement
**Team:** Team Arcane
**Members:** Victor, Peter, Ebenezer, Ebuka, Danny
**Date:** 21st November 2026

---

## Product Overview

Easy Movement is a campus keke (tricycle) booking app for Babcock University. It lets students see which kekes are free, book a ride, know the fare before they ride, and pay inside the app. Drivers receive ride requests on a simple dashboard, and the transport manager gets one place to manage drivers, fares, and bookings.

---

## Problem Statement

Students at Babcock struggle to find a keke, especially after lectures and at busy times. They wait at pickup points, walk around looking for one, or ask other students if they have seen one. Sometimes this makes them late for class.

Payment is the second problem. Fares are not always clear before the ride, many students do not have change, and fare arguments with drivers are common. Drivers lose time driving around looking for passengers, and the transport manager has no record of what is happening.

In short, there is no organised way for students, drivers, and the transport office to connect on campus.

---

## Proposed Solution

A simple mobile app where registered students can see available kekes, book a ride between fixed campus locations, see the fare upfront, and pay in the app. Verified drivers accept or decline requests and mark their availability. Admins approve drivers, set fares, and monitor bookings.

---

## Business Objectives

1. Cut the average time a student waits for a keke from about 12 minutes to under 5 minutes.
2. Show the fare before every ride, so fare arguments stop.
3. Move at least 60% of rides from cash to in-app payment.
4. Give drivers steady, organised ride requests, with at least 70% of verified drivers using the app each week.
5. Give the transport manager one dashboard to manage drivers, fares, and bookings.

---

## Target Users and Stakeholders

**Students (main users).** Any Babcock student who needs to get to lectures, the hostel, the cafeteria, or the library. They want a quick, reliable ride without searching for one. They are frustrated by long waits, not knowing the fare, and cash and change problems.

**Drivers (keke operators).** The operators who carry students around campus. They want more passengers, clear ride requests, and easy, fair payment. They are frustrated by driving around looking for passengers and by arguments over payment.

**Admin (transport manager).** The person in charge of campus transport. They want to manage drivers, set fares, and see how the service is doing. They are frustrated by not being able to monitor drivers and by handling complaints without records.

**Other stakeholders.** The university management, who must approve the system, and the payment provider, who handles the money.

---

## Research and Survey Findings

We are collecting information in two ways: a Google Form for students, and short interviews with students and drivers. Our target is 60 student responses and 10 driver interviews.

**How students cope today:** they wait at pickup points, walk around looking for a keke, or ask other students.

**What is wrong with these options:**

1. Waiting at pickup points is unpredictable, especially at busy times.
2. Searching for a keke wastes time, with no guarantee of finding one.
3. Verbal deals with drivers are hard to track.
4. Cash payment leads to fare arguments and change problems.

**Our working figures from early observation and conversations** (we will update these as the survey closes):

- Students wait about 12 minutes for a keke on average, and 15 to 20 minutes right after lectures.
- The hardest places to get a keke from are the hostels and the lecture halls at the end of classes.
- About 8 out of 10 students say they would book through an app.
- About 6 out of 10 students say they would pay digitally.

---

## User Stories

A user story says what a person wants and why, in the form *"As a [user], I want [something] so that [benefit]."*

### Students

1. As a student, I want to sign up and log in with my school details so that only real Babcock students use the app.
2. As a student, I want to see which kekes are free right now so that I don't waste my break waiting at the junction.
3. As a student, I want to pick where I am and where I'm going so that the driver knows exactly where to find me.
4. As a student, I want to see the fare before I book so that there are no surprises or arguments at the end.
5. As a student, I want to pay in the app so that I don't have to look for change.
6. As a student, I want to see what is happening with my booking so that I know if my ride has been accepted and is on its way.
7. As a student, I want to follow my keke on the map so that I know when to be at the pickup point.
8. As a student, I want to cancel a booking before the driver arrives so that I'm not stuck if my plans change.
9. As a student, I want to set my location by hand when GPS is wrong so that I can still get picked up.

### Drivers

10. As a driver, I want to sign up and be verified so that students trust me.
11. As a driver, I want to switch between "available" and "offline" so that I only get requests when I'm ready to work.
12. As a driver, I want to see the pickup point, destination, and fare for each request so that I can decide quickly.
13. As a driver, I want to accept or decline a request so that I stay in control of my day.
14. As a driver, I want to mark when I have picked up and dropped off a student so that the ride record is correct.
15. As a driver, I want to be paid through the app so that I don't depend on students having change.

### Admin

16. As an admin, I want to approve or reject driver applications so that only trusted drivers carry students.
17. As an admin, I want to set and update fares so that pricing stays fair and the same for everyone.
18. As an admin, I want to see all bookings and their status so that I can monitor the service.
19. As an admin, I want to suspend a driver or student account so that I can act on serious complaints.

### Acceptance criteria for key stories

**Story 4: Seeing the fare before booking.**

- The student must have chosen both a pickup point and a destination.
- The fare must be shown before the student confirms the booking.
- The fare shown must be the fare charged, even if the admin changes fares afterwards.
- If a location is missing, the app asks the student to complete it.

**Story 13: Accepting or declining a request.**

- The driver must be verified and set to available.
- When the driver accepts, the request is locked to that driver and the student is told straight away.
- If the driver declines or does not respond within 60 seconds, the request goes to the next available driver.
- If another driver already accepted, the driver is told the ride is no longer available.

**Story 16: Approving a driver.**

- A new driver stays "Pending" until the admin approves the application.
- A pending or rejected driver cannot receive requests or appear in the available list.
- The driver is notified of the decision.

---

## Functional Requirements

Functional requirements describe what the system must do.

1. Students can register and log in with their school email or student ID and a password.
2. Drivers can register and log in separately from students.
3. Users can reset a forgotten password.
4. Each user has one role (student, driver, or admin) and only sees the screens for that role.
5. A new driver stays "Pending" until an admin approves them.
6. Admins can approve or reject driver applications.
7. Drivers can set their status to Available or Offline.
8. Students can see a list of available kekes. Drivers who are offline or on a ride are not shown.
9. Students choose a pickup point and destination from the list of fixed campus locations.
10. Students can set their pickup location by hand if GPS is inaccurate.
11. The system calculates the fare from the route, using the fares set by the admin.
12. The student sees the fare before confirming the booking.
13. The system sends each booking request to available drivers.
14. Drivers can accept or decline a request, and the first driver to accept gets the ride.
15. If no driver accepts within 60 seconds, the student is told and can try again or cancel.
16. Students can cancel a booking before the driver arrives.
17. Students can pay for a ride in the app through the approved payment provider.
18. Every payment is recorded as Pending, Successful, or Failed, and a failed payment can be retried on the same booking.
19. Every booking moves through clear statuses: Requested, Accepted, Driver Arriving, In Progress, and Completed (or Cancelled).
20. Students and drivers get a notification each time the status changes.
21. Students can see their keke's position on a map while it is on its way to them.
22. Drivers have a dashboard showing their status, the current request, and the ride in progress.
23. Admins can view, search, and filter all drivers, students, and bookings.
24. Admins can create and edit fares for each route.
25. Admins can suspend, reactivate, or remove accounts.

---

## Non-Functional Requirements

Non-functional requirements describe how well the system must work, with targets we can measure.

1. **Performance:** The main screens (available kekes, booking, status) load in under 3 seconds on a normal campus connection.
2. **Performance:** A new booking request reaches available drivers within 5 seconds.
3. **Low data:** One full booking, from opening the app to payment, uses less than 1 MB of data.
4. **Security:** Passwords are never stored in plain text, and all traffic between the app and the server is encrypted (HTTPS).
5. **Privacy:** Each role only sees the data it needs. Drivers cannot see other drivers' earnings, and students cannot see other students' bookings.
6. **Privacy:** Card details are never stored by our app. They are handled by the payment provider.
7. **Availability:** The service is available at least 99% of the time between 6:00 am and 10:00 pm.
8. **Scalability:** The system handles at least 300 students using it at the same time during peak hours.
9. **Reliability:** A failed payment or a dropped connection never creates a duplicate booking or leaves a booking in an unclear state.
10. **Ease of use:** A student can complete a booking in 4 steps or fewer, and the driver dashboard uses large buttons that are easy to use while on the move.
11. **Compatibility:** The app works on common Android phones, iPhones, and modern mobile browsers.

---

## Scope and Priorities

We used the MoSCoW method to decide what comes first.

**Must have:** sign-up and login, driver verification, available keke list, booking with the fare shown, in-app payment, booking status updates, basic ride tracking, driver dashboard, and admin management of drivers, fares, and bookings.

**Should have:** booking history for students, earnings history for drivers, and complaint handling for admins.

**Could have:** simple reports for the transport manager.

**Won't have in this release:** ride sharing, scheduled bookings, advanced GPS tracking, ratings and reviews, loyalty rewards, and other campuses.

---

## MVP

The first version covers everything marked "Must have" above, so that a student can book and pay for a ride and a driver can accept and complete it. We will launch it with 10 drivers on the busiest routes for a 4-week pilot and widen it once it works.

---

## Success Metrics

Easy Movement is a success if, by the end of the first month:

1. Average waiting time drops from 12 minutes to under 5 minutes.
2. At least 40% of campus keke trips are booked through the app.
3. Transport complaints drop by 50%.
4. At least 7 out of 10 verified drivers (70%) are active on the app each week.
5. At least 60% of app rides are paid in the app instead of cash.

---

## What Could Go Wrong

1. **Drivers may not want to use the app.** We will keep it very simple and involve drivers from the start.
2. **Campus internet can be slow.** We will keep the app light so it works on little data.
3. **Some students prefer cash.** We will make in-app payment quick and safe so students feel comfortable.
4. **GPS may not always be accurate.** Students can choose fixed pickup points or set their location by hand.
5. **Drivers may not always be available.** Drivers update their status in the app so students always know who is free.
6. **The payment provider may have problems.** We will allow retries and show clear messages when a payment fails.

---

## Assumptions and Open Questions

**What we are assuming:**

1. Students and drivers have smartphones.
2. The university allows this system on campus.

**What is still unconfirmed:**

1. Which payment provider and payment methods will we use first?
2. Who checks driver documents, and what exactly must a driver provide?
3. Which pickup points will we launch with?
4. Will the university give official approval and agree on how student data is handled?

---

## Next Steps

1. Interview students and drivers.
2. Observe campus transport patterns.
3. Confirm the features and finalise this document.
4. Check payment and university requirements.
5. Build the MVP.
6. Pilot with 10 participating drivers.
