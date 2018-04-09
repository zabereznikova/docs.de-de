## <a name="introduction"></a>Einführung
Neuzuweisungsänderungen wirken sich auf Apps aus, die für eine andere .NET Framework-Instanz neu kompiliert wurden. Dazu zählen:

* Änderungen in der Entwurfszeitumgebung. Beispielsweise können Buildtools Warnungen ausgeben, obwohl dies zuvor nicht der Fall war.

* Änderungen in der Laufzeitumgebung. Dies betrifft nur Apps, die speziell diese .NET Framework-Instanz als Ziel verwenden. Apps, die auf frühere Versionen von .NET Framework abzielen, verhalten sich so, als würden sie in diesen Versionen ausgeführt.

In den Artikeln, in denen Neuzuweisungsänderungen beschrieben werden, haben wir die einzelnen Punkte entsprechend ihrer erwarteten Auswirkung eingestuft:

**Größer** Dies ist eine wesentliche Änderung, die viele Apps beeinträchtigt oder erhebliche Änderungen des Codes erforderlich macht.

**Kleiner** Dies ist eine Änderung, die eine kleine Anzahl von Apps beeinträchtigt oder geringfügige Änderungen des Codes erforderlich macht.

**Grenzfall** Diese Änderung beeinträchtigt Apps nur in sehr spezifischen Szenarien, die nicht häufig vorkommen.

**Transparent** Diese Änderung hat keine nennenswerten Auswirkungen, die Entwickler oder Benutzer beachten müssten. Die App sollte keine Änderung benötigen.
