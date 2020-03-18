---
ms.openlocfilehash: da79a19b3276f6fd2d679eb98406dd85e2a19948
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "70997624"
---
### <a name="apps-published-with-clickonce-that-use-a-sha-256-code-signing-certificate-may-fail-on-windows-2003"></a>Mit ClickOnce veröffentlichte Apps, die ein SHA-256-Codesignaturzertifikat verwenden, verursachen unter Windows 2003 möglicherweise einen Fehler

|   |   |
|---|---|
|Details|Die ausführbare Datei ist mit SHA256 signiert. Früher wurde sie mit SHA1 signiert, unabhängig davon, ob das Codesignaturzertifikat SHA-1 oder SHA-256 war. Dies gilt für:<ul><li>Alle Anwendungen, die mit Visual Studio 2012 oder höher erstellt wurden.</li><li>Anwendungen, die mit Visual Studio 2010 oder früher auf Systemen mit vorhandenem .NET Framework 4.5 erstellt wurden.</li></ul>Darüber hinaus wird das ClickOnce-Manifest, wenn .NET Framework 4.5 oder höher vorhanden ist, auch mit SHA-256 für SHA-256-Zertifikate signiert, unabhängig von der .NET Framework-Version, mit der es kompiliert wurde.|
|Vorschlag|Die Änderung bei der Signierung der ausführbaren ClickOnce-Datei betrifft nur Windows Server 2003-Systeme. Für diese ist die Installation von KB 938397 erforderlich. Die Änderung bei der Signierung des Manifests mit SHA-256, selbst wenn eine App auf .NET Framework 4.0 oder frühere Versionen abzielt, führt eine Laufzeitabhängigkeit von .NET Framework 4.5 oder einer höheren Version ein.|
|`Scope`|Edge|
|Version|4.5|
|Geben Sie Folgendes ein:|Neuzuweisung|
