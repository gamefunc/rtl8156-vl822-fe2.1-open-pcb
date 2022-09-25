# pcb_rtl8156-vl822-fe2.1

verify pass;

rtl8156 2.5g usb netcard;

vl822 4 port usb3.2(usb 3 gen2) hub;

fe2.1 usb2 7 port hub;

pcb online view: https://oshwhub.com/gamefunc/rtl8156-vl822-fe2.1-quan-yan-zheng-wan-bi

maybe this link direct view pcb: https://pro.lceda.cn/editor#id=1934a4245f3142a6956326d20a553307

or use jlc_eda_pro open: pcext_10.6_rtl8156+vl822+fe2.1.eprj

not need: ALL FLASH CHIP AND FIRMWARE; 



# any:
my project support rtl8156B and rtl8156B"S";

"S" version "S" = supply, chip have built in SW(switch) 3.3V && SW 0.95V;

S version Pin 5, input: highV = enable built in SW power regulator, lowV = disable;

notS version Pin 5, output: highV = now give rtl8156 0.95v, use to control SW/LDO chip EN pin;

my project pin_5: R4.7k to GND;

5v -> ldo -> 3.3v -> ldo -> 0.95v -> CCCCCCCC delay;




# imgs:
pcb+:
![image](https://raw.githubusercontent.com/gamefunc/pcb_rtl8156-vl822-fe2.1/main/imgs/pbc%2B.jpg)

pcb+rtl8156:
![image](https://raw.githubusercontent.com/gamefunc/pcb_rtl8156-vl822-fe2.1/main/imgs/pbc%2Brtl8156.jpg)

pcb-:
![image](https://raw.githubusercontent.com/gamefunc/pcb_rtl8156-vl822-fe2.1/main/imgs/pcb-.jpg)


# test env: z77 + i5_2550k; 1G route;

# verify rtl8156:
![image](https://raw.githubusercontent.com/gamefunc/pcb_rtl8156-vl822-fe2.1/main/imgs/rtl8156_verify_0.jpg)
![image](https://raw.githubusercontent.com/gamefunc/pcb_rtl8156-vl822-fe2.1/main/imgs/rtl8156_verify_1.jpg)
![image](https://raw.githubusercontent.com/gamefunc/pcb_rtl8156-vl822-fe2.1/main/imgs/rtl8156_verify_2.jpg)

# verify vl822:
![image](https://raw.githubusercontent.com/gamefunc/pcb_rtl8156-vl822-fe2.1/main/imgs/vl822_verify_v2.jpg)

# verify fe2.1:
![image](https://raw.githubusercontent.com/gamefunc/pcb_rtl8156-vl822-fe2.1/main/imgs/fe2.1_verify.jpg)


# 经历:
开发这个 rtl8156 2.5G USB3网卡还真是坑坑坑, 这坑还是与难度完全无关, 现时为止百度与G完全找不到8156的原理图和完整datasheet, 这都W首开了;

网上毫无完整DATASHEET和PCB和原理图, 那月初去 realtek 官网发邮件给大陆代理商想要个datasheet pdf看PIN定义, 可惜代理商就个摆设不然就是爷的无回;

发给 realtek 技术支持说要联系代理商签NDA保密才能拿datasheet pdf, 
不过 技术支持 MS/MR顾 还是很好人, datasheet pdf没给, 但给了我 公版图;
同代有rtl8125也是2.5G, pci-e的, 立创有PDF, 那PIN定义对照下, 不清晰的定义用保留飞线空间的手法去画即可;

然后开画, 封装标准版那里看到有3个非官方的, 都一样, 导入到专业版花了1小时画好,
画了2个版本无非就供电一个DCDC一个LDO,然后白嫖你懂的,顺路去买RTL8156,然后又遇到中秋立创放假板子15号才到;

板子到了, QFN我都最后焊, 零件焊完了, VL822也焊上了, 焊RTL8156发现脚对不齐, 拿起尺子量了量这RTL8156是QFN56 6*6的; 标准版那3个RTL8156库是QFN56 7*7的,明显坑人, 还好白嫖不心痛, 但这月白嫖用光了;

看看活动还没送卷没得再嫖,没办法了只能含泪花了20元去打板,今天到今天焊,一测全OK,还好;以后不浪了;
