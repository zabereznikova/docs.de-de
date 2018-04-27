### <a name="managed-browser-hosting-controls-from-the-net-framework-11-and-20-are-blocked"></a>Verwaltete Browser-Hoststeuerelemente von .NET Framework 1.1 und 2.0 werden blockiert

|   |   |
|---|---|
|Details|Das Hosting dieser Steuerelemente wird in Internet Explorer blockiert.|
|Vorschlag|Internet Explorer kann eine Anwendung, die verwaltete Browserhostingsteuerelemente verwendet, nicht starten. Das vorherige Verhalten kann wiederhergestellt werden, indem der EnableIEHosting-Wert des Registrierungsunterschlüssels <code>HKLM/SOFTWARE/MICROSOFT/.NETFramework</code> für x86-Systeme und für 32-Bit-Prozesse auf x64-Systeme auf <code>1</code> festgelegt wird und indem der <code>EnableIEHosting</code>-Wert des Registrierungsunterschlüssels <code>HKLM/SOFTWARE/Wow6432Node/Microsoft/.NETFramework</code> für 64-Bit-Prozesse auf x64-Systemen auf <code>1</code> festgelegt wird.|
|Bereich|Gering|
|Version|4.5|
|Typ|Laufzeit|

