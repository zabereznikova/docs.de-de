---
ms.openlocfilehash: e613f0c52c77efebf250f5935d5cbfc29bc09a6b
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2019
ms.locfileid: "67802537"
---
### <a name="wpf-printing-stack-update"></a>Update für WPF-Druckstapel

|   |   |
|---|---|
|Details|Die Druck-APIs von WPF, die <xref:System.Printing.PrintQueue?displayProperty=name> verwenden, rufen nun die Paket-API von Windows zum Drucken von Dokumenten statt der veralteten XPS-Druck-API auf. Diese Änderung wurde für die Wartbarkeit durchgeführt. Weder für Benutzer noch für Entwickler sollten Änderungen im Verhalten oder der API-Nutzung sichtbar werden. Der neue Druckstapel wird bei der Ausführung unter Windows 10 Creators Update standardmäßig aktiviert. Der alte Druckstapel funktioniert in älteren Windows-Versionen weiterhin wie zuvor.|
|Vorschlag|Legen Sie den <code>UseXpsOMPrinting</code>-REG_DWORD-Wert des <code>HKEY_CURRENT_USER\Software\Microsoft\.NETFramework\Windows Presentation Foundation\Printing</code>-Registrierungsschlüssels auf <code>1</code> fest, um den alten Stapel in Windows 10 Creators Update zu verwenden.|
|Bereich|Microsoft Edge|
|Version|4.7|
|Typ|Laufzeit|

