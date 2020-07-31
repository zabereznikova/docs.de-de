---
title: 'Entschärfung: Benutzerdefinierte IMessageFilter.PreFilterMessage-Implementierungen'
description: In diesem Artikel erfahren Sie mehr über die benutzerdefinierte Implementierung der Methode „IMessageFilter.PreFilterMessage“ in Windows Forms-Apps, die auf .NET Framework 4.6.1 oder höher ausgerichtet sind.
ms.date: 03/30/2017
ms.assetid: 9cf47c5b-0bb2-45df-9437-61cd7e7c2f4d
ms.openlocfilehash: 5fe7500d3ed6ff293514495df150a747e7946dda
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/20/2020
ms.locfileid: "86475254"
---
# <a name="mitigation-custom-imessagefilterprefiltermessage-implementations"></a>Entschärfung: Benutzerdefinierte IMessageFilter.PreFilterMessage-Implementierungen

In Windows Forms-Apps für .NET Framework-Versionen ab .NET Framework 4.6.1 kann eine benutzerdefinierte <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType>-Implementierung Meldungen beim Aufrufen der Methode <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> sicher filtern, wenn die <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType>-Implementierung:

- Mindestens eine der folgenden Aktionen ausführt:

  - Hinzufügen eines Meldungsfilters durch Aufrufen der <xref:System.Windows.Forms.Application.AddMessageFilter%2A>-Methode.

  - Entfernen eines Meldungsfilters durch Aufrufen der <xref:System.Windows.Forms.Application.RemoveMessageFilter%2A>-Methode. -Methode.

- **Und** Nachrichten durch Aufrufen der <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=nameWithType>-Methode abruft.

## <a name="impact"></a>Auswirkungen

Diese Änderung betrifft nur Windows Forms-Apps, die auf Versionen von .NET Framework ab .NET Framework 4.6.1 ausgerichtet sind.

Für Windows Forms-Apps, die auf vorherige Versionen von .NET Framework ausgerichtet sind, lösen solche Implementierungen in einigen Fällen beim Aufrufen der <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType>-Methode eine <xref:System.IndexOutOfRangeException>-Ausnahme aus.

## <a name="mitigation"></a>Minderung

Ist diese Änderung nicht erwünscht, kann sie in Apps, die für .NET Framework 4.6.1 oder höher konzipiert sind, deaktiviert werden. Dazu muss dem Abschnitt [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) der App-Konfigurationsdatei die folgende Konfigurationseinstellung hinzugefügt werden:

```xml
<runtime>
    <AppContextSwitchOverrides value="Switch.System.Windows.Forms.DontSupportReentrantFilterMessage=true" />
</runtime>
```

Für Apps, die für frühere Versionen des .NET Framework vorgesehen sind, aber unter .NET Framework 4.6.1 oder einer höheren Version ausgeführt werden, kann dieses Verhalten aktiviert werden, indem dem Abschnitt [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) der App-Konfigurationsdatei die folgende Konfigurationseinstellung hinzugefügt wird:

```xml
<runtime>
    <AppContextSwitchOverrides value="Switch.System.Windows.Forms.DontSupportReentrantFilterMessage=false" />
</runtime>
```

## <a name="see-also"></a>Siehe auch

- [Anwendungskompatibilität](application-compatibility.md)
