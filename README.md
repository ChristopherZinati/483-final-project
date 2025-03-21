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


3/21/25 12:05 pm
- normalized the 15 features to the same scale as target label using min-max scaling

before scaling:
                                       min                       max
service                             0.0000                    3.0000
count                               0.0000                 1216.0000
srv_count                           0.0000                 1216.0000
flowEnd                    1583854854.0937           1583862251.6862
f_octetTotalCount                  86.0000                 3152.0000
msg_size                           32.0000                 2192.0000
pktTotalCount                       1.0000                   17.0000
octetTotalCount                    86.0000                 3314.0000
avg_ps                             86.0000                  490.5000
min_msg_size                       28.0000                  272.0000
b_octetTotalCount                   0.0000                  643.0000
f_rate            8599999999999998976.0000 33799999999999995904.0000
b_flowStart                         0.0000           1583862251.6862
b_pktTotalCount                     0.0000                    1.0000
flags                               0.0000                    1.0000
label                               0.0000                    1.0000

after scaling:

                                       min                       max
service                             0.0000                    1.0000
count                               0.0000                    1.0000
srv_count                           0.0000                    1.0000
flowEnd                             0.0000                    1.0000
f_octetTotalCount                   0.0000                    1.0000
msg_size                            0.0000                    1.0000
pktTotalCount                       0.0000                    1.0000
octetTotalCount                     0.0000                    1.0000
avg_ps                              0.0000                    1.0000
min_msg_size                        0.0000                    1.0000
b_octetTotalCount                   0.0000                    1.0000
f_rate                              0.0000                    1.0000
b_flowStart                         0.0000                    1.0000
b_pktTotalCount                     0.0000                    1.0000
flags                               0.0000                    1.0000