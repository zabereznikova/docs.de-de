---
ms.openlocfilehash: e42bce91afab68e509cb35a8992fa3ca2f096872
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496157"
---
### <a name="wpf-printing-stack-update"></a>Update für WPF-Druckstapel

#### <a name="details"></a>Details

Die Druck-APIs von WPF, die <xref:System.Printing.PrintQueue?displayProperty=fullName> verwenden, rufen nun die Paket-API von Windows zum Drucken von Dokumenten statt der veralteten XPS-Druck-API auf. Diese Änderung wurde für die Wartbarkeit durchgeführt. Weder für Benutzer noch für Entwickler sollten Änderungen im Verhalten oder der API-Nutzung sichtbar werden. Der neue Druckstapel wird bei der Ausführung unter Windows 10 Creators Update standardmäßig aktiviert. Der alte Druckstapel funktioniert in älteren Windows-Versionen weiterhin wie zuvor.

#### <a name="suggestion"></a>Vorschlag

Legen Sie den <code>UseXpsOMPrinting</code>-REG_DWORD-Wert des <code>HKEY_CURRENT_USER\Software\Microsoft\.NETFramework\Windows Presentation Foundation\Printing</code>-Registrierungsschlüssels auf <code>1</code> fest, um den alten Stapel in Windows 10 Creators Update zu verwenden.

| Name    | Wert       |
|:--------|:------------|
| Bereich   |Microsoft Edge|
|Version|4.7|
|Typ|Laufzeit|

#### <a name="affected-apis"></a>Betroffene APIs

Nicht über API-Analyse erkennbar.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
