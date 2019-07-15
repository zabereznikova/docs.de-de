---
ms.openlocfilehash: dd4e387f798b3f93f3eabccb5357399fbe5a4fc1
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2019
ms.locfileid: "67804501"
---
### <a name="apps-published-with-clickonce-that-use-a-sha-256-code-signing-certificate-may-fail-on-windows-2003"></a>Mit ClickOnce veröffentlichte Apps, die ein SHA-256-Codesignaturzertifikat verwenden, verursachen unter Windows 2003 möglicherweise einen Fehler

|   |   |
|---|---|
|Details|Die ausführbare Datei ist mit SHA256 signiert. Früher wurde sie mit SHA1 signiert, unabhängig davon, ob das Codesignaturzertifikat SHA-1 oder SHA-256 war. Dies gilt für:<ul><li>Alle Anwendungen, die mit Visual Studio 2012 oder höher erstellt wurden.</li><li>Anwendungen, die mit Visual Studio 2010 oder früher auf Systemen mit vorhandenem .NET Framework 4.5 erstellt wurden.</li></ul>Darüber hinaus wird das ClickOnce-Manifest, wenn .NET Framework 4.5 oder höher vorhanden ist, auch mit SHA-256 für SHA-256-Zertifikate signiert, unabhängig von der .NET Framework-Version, mit der es kompiliert wurde.|
|Vorschlag|Die Änderung bei der Signierung der ausführbaren ClickOnce-Datei wirkt sich nur auf Windows Server 2003-Systeme aus. Für diese ist die Installation von „KB 938397“ erforderlich. Durch die Änderung bei der Signierung des Manifests mit SHA-256 wird selbst dann eine Laufzeitabhängigkeit von .NET Framework 4.5 oder einer höheren Version eingeführt, wenn eine App .NET Framework 4.0 oder eine niedrigere Version als Zielplattform verwendet.|
|Bereich|Microsoft Edge|
|Version|4.5|
|Typ|Neuzuweisung|

