# Leak report

The only memory leak was "cleaned" in the method is_clean. The memory is originally allocated in strip for the result. Then it is used in is_clean with the name cleaned, but it is never freed after being used. To fix the issue, the length of cleaned, because it is possible that it is an empty string and no memory was allocated. If it is not empty, then free cleaned.

