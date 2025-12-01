## Bluesky Data Pipeline

This project is an end-to-end pipeline for collecting, storing, analyzing, and visualizing posts from the Bluesky social network. It shows how live social media data can flow from a WebSocket feed into a database, be analyzed, and finally explored in an interactive dashboard.

## How It Works

Producer:
Connects to Bluesky’s feed and streams new posts in real time, sending them to a Kafka topic. This is the first step, because without it, no data flows through the pipeline.

Consumer:
Reads messages from Kafka and stores them in a DuckDB database. Each post is saved with metadata, creating a reliable history of events.

Embeddings:
Extracts the text from posts and computes semantic embeddings with a pre-trained model. These vectors make it easy to compare, search, or analyze posts based on meaning.

Sentiment Analysis:
Scores each post for sentiment (positive, negative, neutral) and stores both labels and numeric scores in the database. This adds an emotional dimension to the data.

Dashboard:
Provides an interactive interface to explore the data: see sentiment distributions, top positive/negative posts, and a word cloud of common words.

## Running the Pipeline

Start the producer to stream data, then run the consumer to store it. After you have some posts collected, run embeddings and sentiment analysis to process the content. Finally, open the dashboard to explore the results visually.

This pipeline demonstrates a full real-time data workflow, from ingesting live posts to analyzing content and visualizing insights.

## Visualizations
<img width="1117" height="920" alt="Screenshot 2025-12-01 at 11 14 20 AM" src="https://github.com/user-attachments/assets/9480fc89-1d89-4fee-a6c8-0703c4ccffa1" />
<img width="1473" height="655" alt="Screenshot 2025-12-01 at 11 34 46 AM" src="https://github.com/user-attachments/assets/811bdac4-54b5-4add-94ea-fd181ac16e96" />
<img width="1231" height="511" alt="Screenshot 2025-12-01 at 11 34 55 AM" src="https://github.com/user-attachments/assets/c95f7e90-5d1c-4868-908f-705e59729b66" />
<img width="1081" height="562" alt="Screenshot 2025-12-01 at 11 35 04 AM" src="https://github.com/user-attachments/assets/4576ead0-d3f9-48d5-b050-0ee02f5a5e77" />

