---
title: 'Entschärfung: Benutzerdefinierte IMessageFilter.PreFilterMessage-Implementierungen'
ms.date: 03/30/2017
ms.assetid: 9cf47c5b-0bb2-45df-9437-61cd7e7c2f4d
ms.openlocfilehash: 7757e8d1fd0258ab2d972b7321082e4afa37f710
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "79398646"
---
# <a name="mitigation-custom-imessagefilterprefiltermessage-implementations"></a>Entschärfung: Benutzerdefinierte IMessageFilter.PreFilterMessage-Implementierungen

In Windows Forms-Apps für .NET Framework-Versionen ab .NET Framework 4.6.1 kann eine benutzerdefinierte <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType>-Implementierung Meldungen beim Aufrufen der Methode <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> sicher filtern, wenn die <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType>-Implementierung:

- Mindestens eine der folgenden Aktionen ausführt:

  - Hinzufügen eines Meldungsfilters durch Aufrufen der <xref:System.Windows.Forms.Application.AddMessageFilter%2A>-Methode.

  - Entfernen eines Meldungsfilters durch Aufrufen der <xref:System.Windows.Forms.Application.RemoveMessageFilter%2A>-Methode. -Methode.

- **Und** Nachrichten durch Aufrufen der <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=nameWithType>-Methode abruft.

## <a name="impact"></a>Auswirkungen

Diese Änderung betrifft nur Windows Forms-Apps, die auf Versionen von .NET Framework ab .NET Framework 4.6.1 ausgerichtet sind.

Für Windows Forms-Apps, die auf vorherige Versionen von .NET Framework ausgerichtet sind, lösen solche Implementierungen in einigen Fällen beim Aufrufen der <xref:System.IndexOutOfRangeException>-Methode eine <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType>-Ausnahme aus.

## <a name="mitigation"></a>Minderung

Ist diese Änderung nicht erwünscht, kann sie für Apps, die für .NET Framework 4.6.1 oder höhere Versionen vorgesehen sind, deaktiviert werden. Dazu muss dem Abschnitt [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) der App-Konfigurationsdatei die folgende Konfigurationseinstellung hinzugefügt werden:

```xml
<runtime>
    <AppContextSwitchOverrides value="Switch.System.Windows.Forms.DontSupportReentrantFilterMessage=true" />
</runtime>
```

Für Apps, die für frühere Versionen von .NET Framework vorgesehen sind, aber unter .NET Framework 4.6.1 oder einer höheren Version ausgeführt werden, kann dieses Verhalten aktiviert werden, indem dem Abschnitt [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) der App-Konfigurationsdatei die folgende Konfigurationseinstellung hinzugefügt wird:

```xml
<runtime>
    <AppContextSwitchOverrides value="Switch.System.Windows.Forms.DontSupportReentrantFilterMessage=false" />
</runtime>
```

## <a name="see-also"></a>Weitere Informationen

- [Anwendungskompatibilität](application-compatibility.md)
