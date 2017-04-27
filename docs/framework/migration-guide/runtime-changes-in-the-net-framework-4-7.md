---
title: "Laufzeitänderungen in .NET Framework 4.7 | Microsoft-Dokumentation"
ms.custom: 
ms.date: 04/07/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- runtime changes,.NET Framework
- runtime changes,.NET Framework 4.7
- application compatibility
ms.assetid: 268eb334-7906-4e0b-a1e3-c74b745de2a5
caps.latest.revision: 8
author: rpetrusha
ms.author: ronpet
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 321ec8f8293afad0f3da7fb6f907f45d404394cc
ms.lasthandoff: 04/18/2017

---
# <a name="runtime-changes-in-the-net-framework-47"></a>Laufzeitänderungen in .NET Framework 4.7

In seltenen Fällen können sich Laufzeitänderungen auf vorhandene Apps auswirken, die auf frühere Versionen von .NET Framework abzielen, jedoch in einer älteren .NET Framework-Laufzeit ausgeführt werden. Sie umfassen auch Unterschiede im Verhalten zwischen Anwendungen, die in verschiedenen .NET Framework-Laufzeitumgebungen ausgeführt werden. .NET Framework 4.6.2 umfasst Änderungen in den folgenden Bereichen:

- [Windows Presentation Foundation (WPF)](#WPF)

Die Spalte "Umfang" in den folgenden Tabellen gibt den Schweregrad der einzelnen Änderungen an:

- Schwerwiegend. Eine wesentliche Änderung, die viele Apps beeinflusst oder erhebliche Änderungen des Codes erforderlich macht. Beachten Sie, dass keine der Neuausrichtungsänderungen in diese Kategorie fallen.

- Gering. Eine Änderung, die entweder eine kleine Anzahl von Apps beeinflusst oder geringfügige Änderungen des Codes erforderlich macht.

- Grenzfall. Eine Änderung, die nur Apps in sehr spezifischen Szenarien beeinflusst, die nicht üblich sind.

- Transparent. Eine Änderung, die keine nennenswerten Auswirkungen hat, die Entwickler oder Benutzer beachten müssten. Die App sollte keine Änderung benötigen.

## <a name="a-namewpf--windows-presentation-foundation-wpf"></a><a name="WPF" /> Windows Presentation Foundation (WPF)

assetId:///M:System.Windows.Controls.DataGridCellsPanel.BringIndexIntoView(System.Int32)?qualifyHint=False&autoUpgrade=True

| Funktion | Änderung | Auswirkungen | Bereich |
|---|---|---|---|
| <xref:System.Windows.Controls.DataGridCellsPanel.BringIndexIntoView%2A>-Methode | In .NET Framework 4.6.2 wird die <xref:System.Windows.Controls.DataGridCellsPanel.BringIndexIntoView%2A>-Methode asynchron ausgeführt, wenn Spaltenvirtualisierung aktiviert ist, die Spaltenbreiten aber nicht festgelegt wurden. Wenn Spalten entfernt werden, bevor der asynchrone Vorgang abgeschlossen ist, kann eine <xref:System.ArgumentOutOfRangeException>-Ausnahme auftreten.<br/></br>Ab .NET Framework 4.7 wird die Ausnahme in diesem Szenario nicht mehr ausgelöst. | Diese Änderung erhöht die Zuverlässigkeit der Methode. | Edge | 
|<xref:System.Windows.Controls.Ribbon.RibbonGroup>-Hintergrund | In .NET Framework 4.6.2 und früheren Versionen wurde der <xref:System.Windows.Controls.Ribbon.RibbonGroup>-Hintergrund in lokalisierten Builds mit einem transparenten Pinsel gezeichnet, was zu einem unbefriedigenden Eindruck der Benutzeroberfläche führte. In .NET Framework 4.7 aktualisiert WPF die lokalisierten Ressourcen für das <xref:System.Windows.Controls.Ribbon.RibbonGroup>-Steuerelement, wodurch sichergestellt ist, dass der richtige Pinsel verwendet wird. | Um das neue Verhalten zu nutzen, führen Sie ein Upgrade auf .NET Framework 4.7 aus. | Edge |
| WPF-Rechtschreibprüfung | Ab .NET Framework 4.6.1 löst die Rechtschreibprüfung in WPF-Anwendungen beim Herunterfahren der Anwendung gelegentlich eine <xref:System.ObjectDisposedException>-Ausnahme aus. <br/><br/>In .NET Framework 4.7 wird die Ausnahme von der Runtime ordnungsgemäß behandelt, wodurch negative Auswirkungen auf Anwendungen vermieden werden. Es ist zu beachten, dass auch weiterhin gelegentlich nicht abgefangene Ausnahmen bei Anwendungen auftreten, die unter einem Debugger ausgeführt werden.  | Um das neue Verhalten zu nutzen, führen Sie ein Upgrade auf .NET Framework 4.7 aus.   | Edge |

## <a name="see-also"></a>Siehe auch

[Anwendungskompatibilität in .NET Framework 4.7](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-7.md)


