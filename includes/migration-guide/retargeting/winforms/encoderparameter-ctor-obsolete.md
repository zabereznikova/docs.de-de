### <a name="encoderparameter-ctor-is-obsolete"></a>EncoderParameter ctor ist veraltet

|   |   |
|---|---|
|Details|Der <xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Int32,System.Int32,System.Int32)>-Konstruktor ist jetzt veraltet und gibt Buildwarnungen aus, wenn er verwendet wird.|
|Vorschlag|Obwohl der <xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Int32,System.Int32,System.Int32)>-Konstruktor weiterhin funktioniert, sollte stattdessen der folgende Konstruktor verwendet werden, um die veraltete Buildwarnung zu vermeiden, wenn Code mit .NET 4.5-Tools erneut kompiliert wird: <xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Drawing.Imaging.EncoderParameterValueType,System.IntPtr)>.|
|Bereich|Gering|
|Version|4.5|
|Typ|Neuzuweisung|
|Betroffene APIs|<ul><li><xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Int32,System.Int32,System.Int32)?displayProperty=nameWithType></li></ul>|

