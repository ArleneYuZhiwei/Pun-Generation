# Pun-Generation
Code for the ACL'18 paper: A Neural Approach to Pun Generation

The code is based on 
https://github.com/tensorflow/nmt

`tf 1.4.1` is required
# Usage
1.nohup python -u -m nmt.nmt \
    --infer_batch_size= \
    --out_dir= backward_model_path \
    --inference_input_file=sample_17\
    --inference_output_file=first_part_file>output1.txt 2>&1 &
    
2.you need to deal with the first_part_file and reverse the generated sentences. 
For example: Transfer the "newa06 a # in  7.0129895" into "in # a newa06".  
And get the dealt_first_part_file.

3.nohup python -u -m nmt.nmt \
    --infer_batch_size=  \
    --out_dir=forward_model_path \
    --inference_input_file=dealt_first_part_file\
    --inference_output_file=second_part_file>output2.txt 2>&1 &
    
4. Cconcatenate the dealt_first_part_file and the second_part_file.
Note: If you are interested in Highlight model, please pay attention to 
Line 616-617 in NewBeamSearch_sample.py.
# BibTex
    @inproceedings{yu2018neural,
      title={A Neural Approach to Pun Generation},
      author={Yu, Zhiwei and Tan, Jiwei and Wan, Xiaojun},
      booktitle={Proceedings of the 56th Annual Meeting of the Association for Computational Linguistics (Volume 1: Long Papers)},
      volume={1},
      pages={1650--1660},
      year={2018}
    }
