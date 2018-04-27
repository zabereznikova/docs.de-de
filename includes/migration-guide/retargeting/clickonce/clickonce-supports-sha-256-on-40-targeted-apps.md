### <a name="clickonce-supports-sha-256-on-40-targeted-apps"></a>ClickOnce unterstützt SHA-256 auf Apps, die auf 4.0 ausgerichtet sind

|   |   |
|---|---|
|Details|Bisher war für ClickOnce-Apps mit einem mit SHA-256 signierten Zertifikat auch dann .NET 4.5 oder höher erforderlich, wenn die App auf 4.0 ausgerichtet war. Nun können ClickOnce-Apps, die auf 4.0 ausgerichtet sind, auch dann auf 4.0 ausgeführt werden, wenn sie mit SHA-256 signiert sind.|
|Vorschlag|Diese Änderung beseitigt diese Abhängigkeit und ermöglicht die Verwendung von SHA-256-Zertifikaten zum Signieren von ClickOnce-Apps, die auf .NET Framework 4 und frühere Versionen ausgerichtet sind.|
|Bereich|Gering|
|Version|4.6|
|Typ|Neuzuweisung|

