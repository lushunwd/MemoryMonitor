# MemoryMonitor 

一个给开发者使用的Android App内存清理、监控工具。

可以获取当前手机的内存使用比率，可用内存大小，检查一个APP是否存在内存泄漏。

## 内存清理

类似360卫士的 **加速球**，获取系统已用内存比率、可用内存大小，一键清理。

可以用于测试自己开发的Activity、Fragment健壮性，模拟Activity、Fragment被回收的场景，测试自己的程序是否完好的保存、恢复当前场景。

比如：打开你开发的某个Activity、Fragment，切到后台，清理一次内存，在将其切回前台后，看会不会出现空指针异常，以及程序状态是否被恢复。

## 内存监控

Android系统中的内存和Linux系统一样，存在着大量的共享内存。每个APP占内存会有私有和公共的两部分，我们可以通过App的Pss值，可以获取到这两部分内存。

Pss（Proportional Set Size）：实际使用的物理内存，即：自身应用占有的内存+共享内存中比例分配给这个应用的内存。

通过改程序，每隔1秒，获取一次被监控App的Total Pss值。

使用某个功能（可能会导致OOM的那些都要试试），查看Pss是否飙升，或者使用过许久都没有降低。

如果使用后飙升并且长时间都降不下来，那就说明肯定会导致OOM（对象使用过之后还被引用着未释放），如果使用之后Total Pss飙升，但是使用过之后能降下来，也可能会导致OOM，我们还是需要去一点一点排查是什么原因导致的。

如果使用后飙升并且长时间都降不下来，我们就需要使用MAT来进一步分析问题所在。

## 内存优化

我整理了一些开发中可能会导致内存溢出的情况，放在com.cundong.memory.wrong中，并且给出了优化方法，放在com.cundong.memory.right中。

## 截图



## License

    Copyright 2015 Cundong

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
