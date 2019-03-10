---
title: Windows Forms und nicht verwaltete Anwendungen
ms.date: 03/30/2017
helpviewer_keywords:
- ActiveX controls [Windows Forms]
- COM interop [Windows Forms], Windows Forms
- COM [Windows Forms]
- Windows Forms, unmanaged
- Windows Forms, interop
ms.assetid: 81bc100c-fa49-4614-85a6-0f7ab59eac8a
ms.openlocfilehash: 65465f22b1806d385523c894cce2103afe33c2f0
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57702658"
---
# <a name="windows-forms-and-unmanaged-applications"></a>Windows Forms und nicht verwaltete Anwendungen
Windows Forms-Anwendungen und-Steuerelemente können mit einigen Einschränkungen mit nicht verwalteten Anwendungen zusammenarbeiten. In den folgenden Abschnitten werden die von Windows Forms-Anwendungen und -Steuerelementen unterstützten und nicht unterstützten Szenarien und Konfigurationen beschrieben.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Übersicht über Windows Forms und nicht verwaltete Anwendungen](windows-forms-and-unmanaged-applications-overview.md)  
 Bietet allgemeine Informationen zur Verwendung und Implementierung von Windows Forms-Steuerelementen, die in nicht verwalteten Anwendungen verwendet werden können.  
  
 [Vorgehensweise: Unterstützen von COM-Interop durch Anzeigen eines Windows Forms mit der ShowDialog-Methode](com-interop-by-displaying-a-windows-form-shadow.md)  
 Enthält ein Codebeispiel für die Verwendung der <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType>-Methode zum Ausführen eines Windows Forms in einer nicht verwalteten Anwendung.  
  
 [Vorgehensweise: Unterstützen von COM-Interop durch Anzeigen jedes Windows-Formular in einem eigenen Thread](how-to-support-com-interop-by-displaying-each-windows-form-on-its-own-thread.md)  
 Enthält ein Codebeispiel für die Ausführung eines Windows Forms in einem eigenen Thread.  
  
 Siehe auch [Exemplarische Vorgehensweise: Unterstützen von COM-Interop durch Anzeigen jedes Windows-Formular in einem eigenen Thread](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms233639(v=vs.100)).  
  
## <a name="reference"></a>Referenz  
 <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType>  
 Wird zum Erstellen eines separaten Threads für ein Windows Form verwendet.  
  
 <xref:System.Windows.Forms.Application.Run%2A?displayProperty=nameWithType>  
 Startet eine Nachrichtenschleife für einen Thread.  
  
 <xref:System.Windows.Forms.Control.Invoke%2A>  
 Marshallt Aufrufe von einer nicht verwalteten Anwendung für ein Formular.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Verfügbarmachen von .NET Framework-Komponenten in COM](../../interop/exposing-dotnet-components-to-com.md)  
 Bietet allgemeine Informationen zur Verwendung von .NET Framework-Typen in nicht verwalteten Anwendungen.
