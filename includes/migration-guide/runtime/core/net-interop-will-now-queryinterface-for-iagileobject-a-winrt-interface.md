---
ms.openlocfilehash: 150b94b55fa8f2a29f1da7cf7ac7bf6dd06b9666
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621980"
---
### <a name="net-interop-will-now-queryinterface-for-iagileobject-a-winrt-interface"></a>.NET Interop verwendet jetzt QueryInterface für IAgileObject (eine WinRT-Oberfläche)

#### <a name="details"></a>Details

Wenn ein WinRT-Ereignis mit einem .NET-Delegat verwendet wird, nutzt Windows ab .NET Framework 4.8 QI für IAgileObject.  In früheren Versionen von .NET Framework ist bei QI zur Laufzeit ein Fehler aufgetreten, und das Ereignis konnte nicht abonniert werden.<ul><li>[X] Quirking</li></ul>

#### <a name="suggestion"></a>Vorschlag

Wenn die QI für IAgileObject die Ausführung unterbricht, können Sie diesen Code deaktivieren, indem Sie die folgende Konfiguration festlegen. <h4>Methode 1: Umgebungsvariable</h4> Legen Sie die folgende Umgebungsvariable fest: COMPLUS_DisableCCWSupportIAgileObject=1. Diese Methode wirkt sich auf alle Umgebungen aus, die diese Umgebungsvariable erben. Dabei kann es sich um eine einzelne Konsolensitzung handeln oder, wenn Sie die Umgebungsvariable global festlegen, um den gesamten Computer. Beim Namen der Umgebungsvariablen muss die Groß-/Kleinschreibung nicht beachtet werden. <h4>Methode 2: Registrierung</h4> Suchen Sie mit dem Registrierungs-Editor (regedit.exe) nach einem der folgenden Unterschlüssel: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft.NETFramework HKEY_CURRENT_USER\SOFTWARE\Microsoft.NETFramework. Fügen Sie anschließend Folgendes hinzu: Wertname: DisableCCWSupportIAgileObject Typ: DWORD (32 Bit) Wert (auch als REG_WORD bezeichnet) Wert: 1 Mit dem Windows-Tool REG.EXE können Sie diesen Wert über eine Befehlszeilen- oder Skriptumgebung hinzufügen. Zum Beispiel:<pre><code class="lang-console">reg add HKLM\SOFTWARE\Microsoft\.NETFramework /v DisableCCWSupportIAgileObject /t REG_DWORD /d 1&#13;&#10;</code></pre>In diesem Fall wird <code>HKLM</code> anstelle von <code>HKEY_LOCAL_MACHINE</code> verwendet. Verwenden Sie <code>reg add /?</code>, um Hilfe zu dieser Syntax zu erhalten. Beim Namen des Registrierungswerts wird die Groß-/Kleinschreibung nicht beachtet.

| name    | Wert       |
|:--------|:------------|
| Bereich   |Microsoft Edge|
|Version|4.8|
|Typ|Laufzeit|
