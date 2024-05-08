问题1：
    1.AttributeError: ‘FreeTypeFont‘ object has no attribute ‘getsize‘
    这个bug和第一个bug一样都是因为pillow库版本太新出现的问题，最快的方法也是降低版本，
解决1：pip install pillow==9.5.0

问题2：
        #>>>>>>>>>>>>>>>>>>>>>>>>>>
        return np.array(dst_pnts).astype(np.int)
        # >>>>>>>>>>>>>>>>>>>>>>>>>
        return np.array(dst_pnts).astype(np.int32) # 候胜超
        ############################
问题3：
     生成了图像的标签，但是没有生成图像
解决3：opencv生成的图像路径中不能有中文


# 生成普通文本----横板排列
    python main.py
    parser.add_argument("--config", default="example_data/example.py", help="python file path")                     # 生成正常排版的样本
    
    Eg: 生成索书号样本
       step1： 运行 gen_text_enum_text.ipynb 可以生成 多条（可以指定数量）的索书号语料
       step2:  python main.py 可以生成对应的索书号的图像样本+对应的标签json ===>  example.py 中 修改 num_image 的值可以改变生成样本的书数量
       step3:  运行 gen_label_sig.ipynb 可以将step2中的json内容提取出图形对应的标签文件！！

# 生成书脊文本----竖版排列
    python main.py
    parser.add_argument("--config", default="example_data/effect_layout_example.py", help="python file path")     # 生成逆时针90°的样本


