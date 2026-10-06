Problems and Users 
 
    While going to gym is a very honourable goal many people set out for themselves in order to keep themselves healthy, keeping track of what you have done and seeing how your reps have increases over time is not an easy or enjoyable part of it. Often times its either done on paper or done on notes in your phone, but often times as the time in the gym increaees it creates more notes that can be confusing, or harder to keep track of. Further, if these notes get to confusing it could lead to possible mix-up of what exercises were done in previous days, preventing optimal rest time and possibly causing stress on muscles that should be needing rest.

    This is where our app comes in. Our app's goal is to setup an easy way to create and track their routines, preventing an overlap of exercises and allowing user to create an easy progress ramp as they go on. We will be using the wger api to allow users to search for different exercises and add those to their previous and future routines, and store them in MongoDB.

Features

    MVP:
        1. A signed in user can create a work-out routine, with name and description
        2. A signed in user can add exercises to their work-out routine through the wger api database
        3. A signed in user can view their future routines and see the exercises in each one
        4. A signed in user can recorded a completed workout with excercises, sets, reps, and weights used
        5. A signed in user can view their previous workouts to compare their progress over time
        6. A signed in user can edit or delete their routines
        7. A signed in user can search for excerise information through the wger api database while creating or editing thier routine

    Later:
        1. Progress charts showing improvement over time (weight increase/ reps increase)
        2. Social features for sharing workouts with friends
        3. Custom exercise creations (for ones not in wger)
        4. Recommendations for future workout based on previous workouts
        5. Mobile app formatting

Data Model \
    For eash data type, the layout follows (field/type/required)

    User: 
        _id/ObjectID/yes
        username/String/yes
        email/String/yes
        passwordHash/String/yes
        
        A user can own many workouts

        Workout (Future/Current Workouts):
            _id/ObjectID/yes
            userid/ObjectID/yes
            name/String/yes
            description/String/no
            date/Date/yes
            status/String/yes
            exercises/Array/yes
            notes/String/no
            createdAt/Date/yes
            updatedAt/Date/yes

            A workout can contain many exercises

            Exercise Array:
                exerciseID/Number/yes
                exerciseName/String/yes
                sets/Array/yes

                Sets Array:
                    reps/Number/yes
                    weight/Number/yes

        Excerises (To be pulled from to fill Workouts):
            _id/ObjectID/yes
            userid/ObjectID/yes
            wgerid/ObjectID/yes
            name/String/yes
            description/String/no