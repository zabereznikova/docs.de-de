### <a name="deserialization-of-objects-across-appdomains-can-fail"></a>Deserialisierung von Objekten für mehrere Anwendungsdomänen kann einen Fehler auslösen

|   |   |
|---|---|
|Details|In einigen Fällen, in denen eine App zwei oder mehr App-Domänen mit unterschiedlichen Anwendungsbasen verwendet, löst der Versuch, Objekte im logischen Aufrufkontext über App-Domänen hinweg zu deserialisieren, eine Ausnahme aus.|
|Vorschlag|Weitere Informationen finden Sie unter [Minderung: Deserialisierung von Objekten über App-Domänen](~/docs/framework/migration-guide/mitigation-deserialization-of-objects-across-app-domains.md)|
|Bereich|Microsoft Edge|
|Version|4.5.1|
|Typ|Laufzeit|

