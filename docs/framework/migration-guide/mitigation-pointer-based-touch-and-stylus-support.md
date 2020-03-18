---
title: 'Entschärfung: Zeigerbasierte Touch- und Stiftunterstützung'
ms.date: 04/07/2017
helpviewer_keywords:
- retargeting changes
- .NET Framework 4.7 retargeting changes
- WPF retargeting changes
- WPF pointer-based touch and stylus stack
ms.assetid: f99126b5-c396-48f9-8233-8f36b4c9e717
ms.openlocfilehash: 023c38f66611bd0022699d3f62d90c3923585012
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "77094474"
---
# <a name="mitigation-pointer-based-touch-and-stylus-support"></a>Entschärfung: Zeigerbasierte Touch- und Stiftunterstützung

WPF-Anwendungen mit der Zielplattform .NET Framework 4.7, die auf Windows-Systemen ab Windows 10 Creators Update ausgeführt werden, können einen optionalen `WM_POINTER`-basierten WPF-Touch/Stiftstapel aktivieren.

## <a name="impact"></a>Auswirkungen

Entwickler, die nicht explizit die zeigerbasierte Touch/Stift-Unterstützung aktivieren, sollten keine Änderung im WPF-Touch/Stift-Verhalten feststellen.

Im Folgenden sind die aktuell bekannten Probleme beim optionalen `WM_POINTER`-basierten Touch/Stift-Stapel aufgeführt:

- Keine Unterstützung für Freihand in Echtzeit.

   Zwar funktionieren Freihand- und Stift-Plug-Ins nach wie vor, sie werden aber im Benutzeroberflächen-Thread verarbeitet, was zu schlechter Leistung führen kann.

- Verhaltensänderungen aufgrund der Verlagerung von Touch/Stift-Ereignissen zu Mausereignissen.

  - Die Bearbeitung verhält sich möglicherweise anders.

  - Drag/Drop zeigt keine angemessene Rückmeldung bei Toucheingaben. (Dies betrifft keine Stifteingaben.)

  - Drag/Drop kann für Touch/Stift-Ereignisse nicht mehr ausgelöst werden.

      Dadurch kann es vorkommen, dass die Anwendung nicht reagiert, bis die Mauseingabe erkannt wird. Stattdessen sollten Entwickler Drag & Drop über Mausereignisse einleiten.

## <a name="opting-in-to-wm_pointer-based-touchstylus-support"></a>Entscheidung für die WM_POINTER-basierte Touch/Stift-Unterstützung

Entwickler, die diesen Stapel aktivieren möchten, können der *app.config*-Datei ihrer Anwendung Folgendes hinzufügen:

```xml
<configuration>
    <runtime>
        <AppContextSwitchOverrides value="Switch.System.Windows.Input.Stylus.EnablePointerSupport=true"/>
    </runtime>
</configuration>
```

Das Entfernen dieses Eintrags oder das Festlegen seines Werts auf `false` deaktiviert diesen optionalen Stapel.

## <a name="see-also"></a>Weitere Informationen

- [Anwendungskompatibilität](application-compatibility.md)
