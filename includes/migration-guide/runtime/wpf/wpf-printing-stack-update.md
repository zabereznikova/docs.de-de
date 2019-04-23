---
ms.openlocfilehash: 6fafb689af5d50b31b19f5d1fe7090a6c256ca45
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804000"
---
### <a name="wpf-printing-stack-update"></a>Update für WPF-Druckstapel

|   |   |
|---|---|
|Details|Die Druck-APIs von WPF, die <xref:System.Printing.PrintQueue?displayProperty=name> verwenden, rufen nun die Paket-API von Windows zum Drucken von Dokumenten statt der veralteten XPS-Druck-API auf. Diese Änderung wurde für die Wartbarkeit durchgeführt. Weder für Benutzer noch für Entwickler sollten Änderungen im Verhalten oder der API-Nutzung sichtbar werden. Der neue Druckstapel wird bei der Ausführung unter Windows 10 Creators Update standardmäßig aktiviert. Der alte Druckstapel funktioniert in älteren Windows-Versionen weiterhin wie zuvor.|
|Vorschlag|Legen Sie den <code>UseXpsOMPrinting</code>-REG_DWORD-Wert des <code>HKEY_CURRENT_USER\Software\Microsoft\.NETFramework\Windows Presentation Foundation\Printing</code>-Registrierungsschlüssels auf <code>1</code> fest, um den alten Stapel in Windows 10 Creators Update zu verwenden.|
|Bereich|Microsoft Edge|
|Version|4.7|
|Typ|Laufzeit|
