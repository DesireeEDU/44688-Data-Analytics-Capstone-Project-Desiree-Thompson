# 44688 Data Analytics Capstone Project - Desiree Thompson

**Project Title: Body Fat Estimation in Competitive Physique Athletes**

**Description:**


**Features:**

- Item 1
- Item 2
- Item 3
- Item 4
- Item 5

**Usage:**

1. Step 1

2. Step 2

   ```
   pip install -r requirements.txt
   ```

3. Run the Program:

   - Item 1
   - Item 2

     ```
     python bbq_monitoring.py
     ```

   ![Console Screenshot](https://.png)

4. Monitor RabbitMQ Queues:

   - When prompted, you can choose to monitor RabbitMQ queues by typing `y`.
   - This will open the RabbitMQ Admin interface in your default web browser.

   \*Note:

   - The program will prompt you to monitor RabbitMQ queues. This prompt is controlled by the `show_offer` parameter in the `offer_rabbitmq_admin_site` function.
   - By default, `show_offer` is set to `True`, meaning you will be asked if you want to monitor the queues. You can change this behavior by setting `show_offer` to `False` when calling the function.

5. Consumer Implementation:

   - Three callback functions are implemented to handle messages from each queue: `smoker_callback`, `foodA_callback`, and `foodB_callback`.
   - Each callback function processes the received message, extracts the timestamp and temperature, and stores them in a deque with a specific maximum length.
   - If the conditions for generating alerts are met, the system logs the appropriate alert message.
   - The main function sets up connections to the RabbitMQ server, declares the listening queues, and starts consuming messages from each queue.

   Conditions:

   - Smoker temperature decreases by more than 15 degrees F in 2.5 minutes (smoker alert)
   - Any food temperature changes less than 1 degree F in 10 minutes (food stall alert)

**File Structure:**

- `requirements.txt`: File listing the dependencies required by the project.

**Customization:**


**Note:**

**Author:**
Desiree Thompson

**Date:**

**Acknowledgments:**

- The project utilizes ChatGPT, an AI language model developed by OpenAI, for assistance in writing the README and providing guidance on software engineering practices.
