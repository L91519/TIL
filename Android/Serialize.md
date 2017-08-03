# Serialize

직렬화

I had to search about this while sending data with intent.

I had a ArrayList which contains a class.

And an error occured because that certain class wasn't serialized and when a class is not serialized, it is difficult to send a data.

 implement Serializable.

SuppressWarnings("serial");

+ Actually when we use that serializable, we need serialVersionUID but android doesn't support this. So instead of serialVersionUID, we use annotation.