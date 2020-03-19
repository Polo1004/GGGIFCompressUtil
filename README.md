# GGGIFCompressUtil
利用 ImageIO 对GIF图进行压缩

先进行抽帧操作（抽一半），抽帧压缩效率很高，所以首先进行

若抽帧后大小仍达不到目标大小，则进行分辨率压缩（直到符合目标大小）



### 用法

```objective-c
// data：源GIF Data 
// targetSize：目标分辨率（最终结果不一定是这个）
// targetByte：目标字节数（1M = 1 * 1024 * 1024）
GGGIFCompressUtil *gifCompressUtil = [[GGGIFCompressUtil alloc] initWithImageData:data targetSize:CGSizeMake(asset.pixelWidth, asset.pixelHeight) targetByte:4.5 * 1024 * 1024];

[gifCompressUtil compressAsynchronouslyWithCompletionHandler:^(NSData * _Nullable compressedData, CGSize gifImageSize, NSError * _Nullable error) {
    // 压缩后操作                                       
}];
```

