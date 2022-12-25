```csharp
public static int MaxWantedLevel
{
	get
	{
		return Function.Call<int>(Hash.GET_MAX_WANTED_LEVEL);
	}
	set
	{
		if (value < 0)
		{
			value = 0;
		}
		if (value > 5)
		{
			value = 5;
		}
		Function.Call(Hash.SET_MAX_WANTED_LEVEL, value);
	}
}
```

Return : int  0 ila 5 arasında bir sayı

Max aranma seviyesini ayarlar.
0'dan küçük bir sayı olarak ayarlarsanız 0 yapar
5'den büyük bir sayı olarak ayarlarsanız 5 yapar.

Max aranma seviyesini kaç yaparsanız o seviyeden üst seviyeye çıkmayacaktır.
Örnek:
`MaxWantedLevel = 0;`
Oyuncunun hiç aranması olmayacaktır. Bu durumda polisi öldürse bile polisler tarafından aranmayacaktır.

![image](https://user-images.githubusercontent.com/63202456/209479212-6995f1c9-9e1e-4ef6-af3c-956e5160773a.png)

