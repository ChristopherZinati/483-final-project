#log all changes to OCPUA dataset here

- MAX_DATA_OATH and CHRIS_DATA_PATH variables set to easily configure paths when working on dataset
- rows with missing values removed and FIRST round of row selection, multi_label, src_ip, src_port, dst_ip, dst_port dropped
- displayed a correlation matrix of all features to the target label. The following are the most relevent
service              0.9992
count                0.8238
srv_count            0.8237
flowEnd             -0.3167
f_octetTotalCount   -0.9842
msg_size            -0.9938
pktTotalCount       -0.9949
octetTotalCount     -0.9953
avg_ps              -0.9956
min_msg_size        -0.9962
b_octetTotalCount   -0.9964
f_rate              -0.9992
b_flowStart         -0.9997
b_pktTotalCount     -0.9997
flags               -1.0000

- displayed a min, max table to check feature range, normalization IS NEEDED check table to see which ones
- created a heatmap to visualize feature correlation, may need to reduce some more features or perform feature extraction to reduce redudancy
- made a new df with only 16 features to reduce dimensionality. Trying to reduce more.
