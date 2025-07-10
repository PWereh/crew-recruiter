resume_task = Task(
    description=resume_text,
    expected_output="Structured resume data",
    agent=resume_parser
)
jd_task = Task(
    description=jd_text,
    expected_output="Structured JD data",
    agent=jd_parser
)
matching_task = Task(
    description="Match resume to JD.",
    expected_output="Match score and insights.",
    agent=matcher,
    context=[resume_task, jd_task]
)