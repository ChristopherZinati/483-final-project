#log all changes to OCPUA dataset here

- MAX_DATA_OATH and CHRIS_DATA_PATH variables set to easily configure paths when working on dataset
- rows with missing values removed and FIRST round of row selection, multi_label, src_ip, src_port, dst_ip, dst_port dropped
- displayed a correlation matrix of all features to the target label. The following are the most relevent
  service 0.9992
  count 0.8238
  srv_count 0.8237
  flowEnd -0.3167
  f_octetTotalCount -0.9842
  msg_size -0.9938
  pktTotalCount -0.9949
  octetTotalCount -0.9953
  avg_ps -0.9956
  min_msg_size -0.9962
  b_octetTotalCount -0.9964
  f_rate -0.9992
  b_flowStart -0.9997
  b_pktTotalCount -0.9997
  flags -1.0000

- displayed a min, max table to check feature range, normalization IS NEEDED check table to see which ones
- created a heatmap to visualize feature correlation, may need to reduce some more features or perform feature extraction to reduce redudancy
- made a new df with only 16 features to reduce dimensionality. Trying to reduce more.

- did standard scaling on data for PCA
- Did PCA, found that there are 2 principal components needed to explain at least 95% of variance

Key features for PC1 (sorted by absolute loadings):
f_rate 0.2710
b_octetTotalCount 0.2708
b_flowStart 0.2708
b_pktTotalCount 0.2708
flags 0.2708
avg_ps 0.2706
min_msg_size 0.2706
service 0.2704
octetTotalCount 0.2702
msg_size 0.2701
pktTotalCount 0.2693
f_octetTotalCount 0.2667
count 0.2373
srv_count 0.2373
flowEnd 0.1070

Key features for PC2 (sorted by absolute loadings):
flowEnd 0.7953
srv_count 0.3790
count 0.3790
avg_ps 0.0845
msg_size 0.0841
b_octetTotalCount 0.0840
min_msg_size 0.0838
octetTotalCount 0.0830
f_rate 0.0819
f_octetTotalCount 0.0806
flags 0.0801
b_pktTotalCount 0.0801
b_flowStart 0.0801
pktTotalCount 0.0797
service 0.0786

- PC1 captures traffic volume metrics
- most important features are f_rate, b_octetTotalCount, b_flowStart, and b_pktTotalCount. all other features have similar loadings here except count, srv_count, and flowEnd

- PC2 captures flow-duration metrics
- most important feature is flowEnd with absolute loading of 0.7953, followed by srv_count and count both with an absolute loading of 0.3790
- all other features here have absolute loadings < 0.0845
