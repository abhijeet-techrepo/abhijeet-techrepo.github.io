# Device Flow Playground

To run the playground locally, simply serve the root directory:

```sh
npx serve
```

```mermaid

erDiagram

  clinic {
    serial clinic_id
    varchar name
  }

  clinician_role {
    serial clinician_role_id
    varchar name
  }

  conversation {
    serial conversation_id
    varchar conversation_sid
    conversation_type_enum type
    conversation_env_enum env
    timestamptz created_at
    timestamptz updated_at
    timestamptz deleted_at
  }

  credential {
    int4 user_id
    varchar password
    varchar login_access_token
    varchar conversation_access_token
    timestamptz created_at
    timestamptz updated_at
    bool is_active
  }

  discover_category {
    serial discover_category_id
    varchar discover_category_name
    timestamptz created_at
    timestamptz deleted_at
  }

  games {
    serial game_id
    varchar description
    varchar name
    varchar status
    timestamptz created_at
    timestamptz updated_at
    timestamptz deleted_at
  }

  medication_icon {
    serial micon_id
    varchar name
    varchar description
    varchar image_url
    timestamptz created_at
    timestamptz updated_at
    timestamptz deleted_at
  }

  migrations {
    serial id
    int8 timestamp
    varchar name
  }

  reminiscence_tag {
    serial rtag_id
    varchar name
    timestamptz created_at
  }

  role {
    serial role_id
    varchar name
    timestamptz createdAt
    timestamptz updatedAt
    jsonb permission
    varchar role_name
  }

  site {
    serial site_id
    varchar name
    varchar location
    timestamptz created_at
    timestamptz updated_at
  }

  symptom {
    serial symptom_id
    varchar name
  }

  task_category {
    serial tcategory_id
    varchar name
    timestamptz created_at
    int4 user_id
    bool is_default
  }

  therapy {
    serial therapy_id
    varchar name
    timestamptz created_at
    timestamptz updated_at
  }

  typeorm_metadata {
    varchar type
    varchar database
    varchar schema
    varchar table
    varchar name
    text value
  }

  discover {
    serial discover_id
    varchar type
    varchar video_url
    varchar video_thumbnail
    varchar image_url
    varchar image_thumbnail
    varchar content_for
    varchar status
    varchar description
    varchar short_description
    varchar topic
    varchar duration
    varchar title
    jsonb required_items
    timestamptz created_at
    timestamptz updated_at
    timestamptz deleted_at
    timestamptz last_visited
    int4 category
  }

  generate_id {
    serial id
    varchar generate_id
    generate_id_role_enum role
    timestamptz created_at
    timestamptz updated_at
    int4 site_id
  }

  learning {
    serial learning_id
    varchar description
    varchar media_description
    varchar media_thumbnail
    varchar media_url
    bool is_test_data
    bool status
    timestamptz created_at
    timestamptz updated_at
    timestamptz deleted_at
    int4 therapyTherapyId
    varchar title
    int4 part
  }

  logs {
    serial log_id
    int4 user_id
    varchar description
    int4 created_by
    timestamptz created_at
    int4 site_id
  }

  reminiscence_therapy {
    serial reminiscence_therapy_id
    varchar description
    timestamptz created_at
    int4 therapy_id
    bool status
  }

  tablet {
    serial tablet_id
    varchar tablet_name
    int4 site_id
  }

  tablet_id {
    serial id
    varchar tablet_id_name
    tablet_id_status_enum status
    int4 site_id
  }

  therapy_games {
    serial therapy_game_id
    varchar description
    varchar status
    int4 therapy_id
    int4 game_id
    timestamptz created_at
    timestamptz updated_at
    timestamptz deleted_at
  }

  user {
    serial user_id
    varchar fullname
    varchar firstname
    varchar lastname
    varchar profile_image
    varchar username
    timestamp last_visited
    timestamp last_viewed
    timestamp last_edited
    timestamp last_online
    timestamp last_called
    timestamptz created_at
    timestamptz updated_at
    timestamp deleted_at
    varchar mobile
    int4 otp
    bool forgot_password_triggered
    varchar email
    timestamp dob
    user_sex_enum sex
    int4 role_id
    int4 site_id
    text notification_setting
    timestamp assessment_submission_date
    timestamp therapy_start_date
    varchar handedness
    int4 assessment_submitted_by
    bool is_final_assessment
    timestamp final_assessment_submission_date
    int4 final_assessment_submitted_by
    bool is_test_user
    text is_agree
  }

  wearable {
    serial wearable_id
    varchar wearable_name
    int4 site_id
  }

  wearable_id {
    serial id
    varchar wearable_id_name
    wearable_id_status_enum status
    int4 site_id
  }

  wellness {
    serial wellness_id
    varchar description
    jsonb required_items
    varchar title
    varchar duration
    varchar media_description
    varchar media_thumbnail
    varchar media_url
    bool is_test_data
    bool status
    timestamptz created_at
    timestamptz updated_at
    timestamptz deleted_at
    int4 therapyTherapyId
    varchar type
  }

  appointment {
    serial appointment_id
    int4 patient_user_id
    timestamptz start_at
    timestamptz start_time
    timestamptz created_at
    timestamptz updated_at
    timestamptz deleted_at
    int4 clinician_user_id
    int4 site_id
    varchar status
    varchar description
    varchar title
    int4 care_team_id
  }

  assign_therapy_logs {
    serial assign_log_id
    int4 patient_id
    int4 modified_by
    int4 week
    timestamptz created_at
  }

  caregiver {
    int4 user_id
    varchar partner_id
  }

  clinician {
    int4 user_id
    varchar clinician_id
    varchar clinic_id
    timestamptz created_at
    timestamptz updated_at
  }

  compliance {
    serial compliance_id
    int4 login_freq
    int4 total_entries
    int4 event1
    int4 event2
    int4 todo1
    int4 todo2
    int4 note1
    int4 note2
    timestamptz random_date_1
    timestamptz random_date_2
    timestamptz next_week
    timestamptz next_month
    int4 compliance_score
    int4 avg_compliance_score
    int4 revised_score
    timestamptz assessed_at
    timestamptz created_at
    int4 user_id
  }

  device {
    serial device_id
    int4 user_id
    varchar device_name
    device_token_type_enum token_type
    varchar device_token
    varchar binding_sid
    varchar user_token
    timestamptz created_at
    timestamptz updated_at
    timestamptz deleted_at
  }

  discover_lesson {
    serial lesson_id
    varchar lesson_title
    int4 discover
    timestamptz created_at
    timestamptz deleted_at
    varchar image_url
    varchar image_thumbnail
    varchar duration
  }

  gratitude {
    serial gratitude_id
    int4 user_id
    jsonb notes
    timestamptz created_at
    timestamptz updated_at
    timestamptz deleted_at
  }

  login_activity {
    serial activity_id
    int4 user_id
    varchar device_name
    varchar uuid
    timestamp login_verified_at
    timestamptz created_at
    timestamptz updated_at
  }

  medication {
    serial medication_id
    int4 user_id
    varchar title
    varchar name
    varchar description
    varchar type
    varchar purpose
    varchar dosage
    varchar dosage_unit
    varchar icon_type
    varchar duration
    varchar duration_description
    timestamptz start_date
    timestamptz end_date
    varchar special_instruction
    timestamptz created_at
    timestamptz updated_at
    timestamptz deleted_at
    int4 created_by
    int4 micon_id
    bool session_alert
  }

  message {
    serial message_id
    varchar message_sid
    varchar body
    message_type_enum type
    int4 message_index
    timestamptz created_at
    timestamptz updated_at
    timestamptz deleted_at
    int4 conversation_id
    int4 user_id
  }

  mood {
    serial mood_id
    timestamptz reported_at
    timestamptz updated_at
    mood_type_enum type
    int4 user_id
  }

  mood_scores {
    serial score_id
    int4 avg_mood
    int4 day
    varchar week
    timestamptz assessed_at
    timestamptz created_at
    int4 user_id
  }

  mss_event_completion {
    serial completion_id
    int4 completion
    int4 avg_completion_rate
    timestamptz assessed_at
    timestamptz created_at
    int4 user_id
  }

  mss_todo_completion {
    serial completion_id
    varchar week
    int4 completion
    timestamptz created_at
    int4 user_id
  }

  notes {
    serial note_id
    int4 words_count
    timestamptz created_at
    timestamptz updated_at
    int4 user_id
  }

  participant_conversation {
    int4 conversation_id
    int4 user_id
    varchar user_participant_sid
    timestamptz created_at
    timestamptz updated_at
    timestamptz deleted_at
  }

  patient {
    int4 user_id
    varchar patient_id
    varchar clinic_patient_id
    int4 consulting_doctor_id
    int4 tablet
    int4 tablet_id
    int4 wearable
    int4 wearable_id
    timestamp deleted_at
    int4 supporting_doctor_id
    text insurance_images
    timestamp insurance_uploaded_at
  }

  post {
    serial post_id
    bool save_post
    bool hide_post
    varchar conversation_sid
    varchar message_sid
    int4 message_index
    int4 user_id
    timestamptz created_at
    timestamptz updated_at
  }

  reminiscence {
    serial reminiscence_id
    varchar description
    timestamptz created_at
    int4 user_id
  }

  reminiscence_topic {
    serial topic_id
    varchar name
    varchar type
    timestamptz created_at
    int4 opinion_id
    int4 reminiscence_topic
  }

  therapy_logs {
    serial log_id
    therapy_logs_type_enum type
    int4 therapy_id
    int4 game_id
    int4 learning_id
    int4 wellness_id
    int4 reminiscence_id
    timestamptz created_at
    timestamptz updated_at
    timestamptz deleted_at
    int4 user_id
    float8 time_spent
    timestamp start_at
    timestamp end_at
  }

  user_detail {
    serial user_detail_id
    int4 user_id
    varchar type
    jsonb assessment
    bool is_final
    timestamptz createdAt
    timestamptz updatedAt
  }

  user_discover {
    int4 discoverDiscoverId
    int4 userUserId
  }

  user_therapy {
    serial user_therapy_id
    int4 therapy_id
    varchar name
    varchar description
    int4 user_id
    user_therapy_status_enum status
    int4 game_progress
    int4 reminiscence_progress
    int4 learning_progress
    int4 wellness_progress
    timestamptz created_at
    timestamptz updated_at
    timestamptz start_at
    timestamptz end_at
    timestamptz locked_at
  }

  alert {
    serial alert_id
    timestamptz created_at
    varchar time
    int4 created_by
    timestamptz alert_at
    int4 medication_id
  }

  calendar_event {
    serial cevent_id
    varchar name
    varchar place
    varchar type
    varchar status
    varchar person
    timestamptz date
    time start_time
    time end_time
    varchar invited_person
    bool set_reminder
    bool inform_partner
    varchar reminder_before_time
    varchar reminder_before_type
    timestamptz created_at
    timestamptz updated_at
    timestamptz completed_at
    timestamptz rejected_at
    timestamptz deleted_at
    int4 medication_id
    jsonb custom_reminder
    int4 created_by
    int4 user_id
    int4 appointment_id
  }

  comment {
    serial comment_id
    varchar body
    comment_type_enum type
    varchar url
    timestamptz created_at
    timestamptz updated_at
    timestamptz deleted_at
    int4 message_id
    int4 user_id
  }

  discover_content {
    serial content_id
    varchar content
    int4 lesson
    int4 page_number
    timestamptz created_at
    timestamptz deleted_at
  }

  discover_progress {
    serial progress_id
    int4 progress
    int4 page_number
    int4 discover
    int4 lesson
    int4 user
  }

  medication_image {
    serial mimage_id
    varchar description
    varchar photo_url
    timestamptz created_at
    timestamptz updated_at
    timestamptz deleted_at
    int4 medication_id
  }

  mood_trigger {
    serial mtrigger_id
    timestamptz createdAt
    timestamptz updatedAt
    int4 rating
    mood_trigger_reason_enum reason
    mood_trigger_feeling_enum feeling
    int4 mood_id
  }

  patient_caregiver_relation {
    serial pcreation_id
    int4 patient_user_id
    int4 caregiver_user_id
    patient_caregiver_relation_relation_enum relation
    varchar custom_relation
    varchar partner_role
    bool lives_with_patient
    varchar time_spent
    timestamptz created_at
    timestamptz updated_at
    timestamp deleted_at
  }

  reminiscence_image {
    serial rimage_id
    varchar description
    varchar image_url
    varchar file_type
    timestamptz created_at
    bool is_image_default
    int4 reminiscence_id
    int4 reminiscence_therapy_id
  }

  symptom_report {
    serial symptom_report_id
    int4 patient_user_id
  }

  task {
    serial task_id
    varchar description
    task_type_enum type
    task_status_enum status
    timestamptz start_at
    timestamptz end_at
    timestamptz created_at
    timestamptz updated_at
    timestamptz deleted_at
    int4 tcategory_id
    int4 user_id
    int4 medication_id
    timestamptz completed_at
    timestamptz cancelled_at
  }

  user_lesson {
    int4 discoverLessonLessonId
    int4 userUserId
  }

  alert_response {
    serial alert_response_id
    timestamptz created_at
    timestamptz taken_at
    int4 alertIdAlertId
  }

  event_history {
    serial event_history_id
    int4 event_id
    int4 alert_id
    timestamptz completed_at
    timestamptz rejected_at
    bool am_reminded
    bool pm_reminded
    timestamptz created_at
  }

  notification {
    serial notification_id
    varchar type
    varchar body
    bool is_read
    bool is_read_by_patient
    bool is_read_by_caregiver
    timestamptz created_at
    timestamptz updated_at
    timestamptz deleted_at
    int4 patient_user_id
    int4 clinician_user_id
    int4 site_id
    int4 appointment_id
    int4 medication_id
    int4 event_id
  }

  patient_symptom {
    serial patient_symptom_id
    int4 user_id
    patient_symptom_rating_enum rating
    timestamptz start_at
    bool is_confirmed
    int4 symptom_id
    timestamptz created_at
    timestamptz updated_at
    timestamptz deleted_at
    int4 confirmed_by
    bool is_acknowledge
    int4 acknowledged_by
    timestamp acknowledged_at
    int4 symptom_report
  }

  question {
    serial question_id
    jsonb options
    jsonb roptions
    question_type_enum type
    jsonb answers
    varchar description
    varchar question
    varchar title
    question_is_single_choice_enum is_single_choice
    int4 order
    timestamptz created_at
    timestamptz updated_at
    timestamptz deleted_at
    int4 learningLearningId
    int4 reminiscence_image
    int4 reminiscence_topic
    int4 reminiscence_therapy_id
  }

  reminder {
    serial reminder_id
    timestamptz createdAt
    timestamptz updatedAt
    timestamptz start_date
    timestamptz end_date
    time start_at
    time end_at
    int4 frequence
    varchar frequency_unit
    int4 created_by
    int4 cevent_id
    int4 medication_id
  }

  reminiscence_tag_image_relation {
    int4 reminiscenceImageRimageId
    int4 reminiscenceTagRtagId
  }

  subtask {
    serial subtask_id
    varchar description
    subtask_status_enum status
    timestamptz created_at
    timestamptz updated_at
    timestamptz deleted_at
    int4 task_id
    timestamptz completed_at
    timestamptz cancelled_at
    int4 step_index
  }

  task_image {
    serial timage_id
    varchar description
    varchar image_url
    timestamptz created_at
    int4 task_id
  }

  question_response {
    serial response_id
    int4 learning_id
    int4 reminiscence_id
    int4 question_id
    int4 therapy_id
    int4 user_id
    jsonb answers
    bool correct
    bool option
    varchar response_file
    question_response_type_enum type
    timestamptz created_at
  }

  patient_list {
    json wearable_list
    json tablet_list
    json medication_list
    json reminder_list
    json mood_score_list
    json compliance_list
    json therapy_list
    jsonb user_list
    json symptom_list
    json relation_list
    json caregiver_list
    json caregiverData_list
    json therapyLogs
    int4 site_id
    bool is_test_user
    timestamptz user_created_at
    int4 patient_user_id
    varchar patient_patient_id
    varchar patient_clinic_patient_id
    int4 patient_consulting_doctor_id
    int4 patient_tablet
    int4 patient_tablet_id
    int4 patient_wearable
    int4 patient_wearable_id
    timestamp patient_deleted_at
  }



  conversation ||--o{ message : "foreign key"
  conversation ||--o{ participant_conversation : "foreign key"


  discover_category ||--o{ discover : "foreign key"

  games ||--o{ therapy_games : "foreign key"
  games ||--o{ therapy_logs : "foreign key"

  medication_icon ||--o{ medication : "foreign key"


  reminiscence_tag ||--o{ reminiscence_tag_image_relation : "foreign key"

  role ||--o{ user : "foreign key"

  site ||--o{ appointment : "foreign key"
  site ||--o{ generate_id : "foreign key"
  site ||--o{ logs : "foreign key"
  site ||--o{ notification : "foreign key"
  site ||--o{ tablet : "foreign key"
  site ||--o{ tablet_id : "foreign key"
  site ||--o{ wearable : "foreign key"
  site ||--o{ wearable_id : "foreign key"

  symptom ||--o{ patient_symptom : "foreign key"

  task_category ||--o{ task : "foreign key"

  therapy ||--o{ learning : "foreign key"
  therapy ||--o{ question_response : "foreign key"
  therapy ||--o{ reminiscence_therapy : "foreign key"
  therapy ||--o{ therapy_games : "foreign key"
  therapy ||--o{ therapy_logs : "foreign key"
  therapy ||--o{ user_therapy : "foreign key"
  therapy ||--o{ wellness : "foreign key"


  discover ||--o{ discover_lesson : "foreign key"
  discover ||--o{ discover_progress : "foreign key"
  discover ||--o{ user_discover : "foreign key"


  learning ||--o{ question : "foreign key"
  learning ||--o{ question_response : "foreign key"
  learning ||--o{ therapy_logs : "foreign key"


  reminiscence_therapy ||--o{ question : "foreign key"
  reminiscence_therapy ||--o{ question_response : "foreign key"
  reminiscence_therapy ||--o{ reminiscence_image : "foreign key"
  reminiscence_therapy ||--o{ reminiscence_topic : "foreign key"
  reminiscence_therapy ||--o{ therapy_logs : "foreign key"

  tablet ||--o{ patient : "foreign key"

  tablet_id ||--o{ patient : "foreign key"


  user ||--o{ alert : "foreign key"
  user ||--o{ appointment : "foreign key"
  user ||--o{ assign_therapy_logs : "foreign key"
  user ||--o{ calendar_event : "foreign key"
  user ||--o{ caregiver : "foreign key"
  user ||--o{ clinician : "foreign key"
  user ||--o{ comment : "foreign key"
  user ||--o{ compliance : "foreign key"
  user ||--o{ device : "foreign key"
  user ||--o{ discover_progress : "foreign key"
  user ||--o{ gratitude : "foreign key"
  user ||--o{ login_activity : "foreign key"
  user ||--o{ medication : "foreign key"
  user ||--o{ message : "foreign key"
  user ||--o{ mood : "foreign key"
  user ||--o{ mood_scores : "foreign key"
  user ||--o{ mss_event_completion : "foreign key"
  user ||--o{ mss_todo_completion : "foreign key"
  user ||--o{ notes : "foreign key"
  user ||--o{ notification : "foreign key"
  user ||--o{ participant_conversation : "foreign key"
  user ||--o{ patient : "foreign key"
  user ||--o{ patient_symptom : "foreign key"
  user ||--o{ post : "foreign key"
  user ||--o{ question_response : "foreign key"
  user ||--o{ reminder : "foreign key"
  user ||--o{ reminiscence : "foreign key"
  user ||--o{ task : "foreign key"
  user ||--o{ therapy_logs : "foreign key"
  user ||--o{ user : "foreign key"
  user ||--o{ user_detail : "foreign key"
  user ||--o{ user_discover : "foreign key"
  user ||--o{ user_lesson : "foreign key"
  user ||--o{ user_therapy : "foreign key"

  wearable ||--o{ patient : "foreign key"

  wearable_id ||--o{ patient : "foreign key"

  wellness ||--o{ therapy_logs : "foreign key"

  appointment ||--o{ calendar_event : "foreign key"
  appointment ||--o{ notification : "foreign key"


  caregiver ||--o{ patient_caregiver_relation : "foreign key"




  discover_lesson ||--o{ discover_content : "foreign key"
  discover_lesson ||--o{ discover_progress : "foreign key"
  discover_lesson ||--o{ user_lesson : "foreign key"



  medication ||--o{ alert : "foreign key"
  medication ||--o{ calendar_event : "foreign key"
  medication ||--o{ medication_image : "foreign key"
  medication ||--o{ notification : "foreign key"
  medication ||--o{ reminder : "foreign key"
  medication ||--o{ task : "foreign key"

  message ||--o{ comment : "foreign key"

  mood ||--o{ mood_trigger : "foreign key"






  patient ||--o{ patient_caregiver_relation : "foreign key"
  patient ||--o{ patient_symptom : "foreign key"
  patient ||--o{ symptom_report : "foreign key"


  reminiscence ||--o{ reminiscence_image : "foreign key"

  reminiscence_topic ||--o{ question : "foreign key"





  alert ||--o{ alert_response : "foreign key"
  alert ||--o{ event_history : "foreign key"

  calendar_event ||--o{ event_history : "foreign key"
  calendar_event ||--o{ notification : "foreign key"
  calendar_event ||--o{ reminder : "foreign key"







  reminiscence_image ||--o{ question : "foreign key"
  reminiscence_image ||--o{ reminiscence_tag_image_relation : "foreign key"

  symptom_report ||--o{ patient_symptom : "foreign key"

  task ||--o{ subtask : "foreign key"
  task ||--o{ task_image : "foreign key"






  question ||--o{ question_response : "foreign key"










```
