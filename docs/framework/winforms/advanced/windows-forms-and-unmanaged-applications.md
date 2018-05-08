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
ms.openlocfilehash: c51645fb64f512b5974000f89e8e98f884a7381d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="windows-forms-and-unmanaged-applications"></a>Windows Forms und nicht verwaltete Anwendungen
Windows Forms-Anwendungen und-Steuerelemente können mit einigen Einschränkungen mit nicht verwalteten Anwendungen zusammenarbeiten. In den folgenden Abschnitten werden die von Windows Forms-Anwendungen und -Steuerelementen unterstützten und nicht unterstützten Szenarien und Konfigurationen beschrieben.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Übersicht über Windows Forms und nicht verwaltete Anwendungen](../../../../docs/framework/winforms/advanced/windows-forms-and-unmanaged-applications-overview.md)  
 Bietet allgemeine Informationen zur Verwendung und Implementierung von Windows Forms-Steuerelementen, die in nicht verwalteten Anwendungen verwendet werden können.  
  
 [Gewusst wie: Unterstützen von COM-Interop durch Anzeigen eines Windows Forms mit der ShowDialog-Methode](../../../../docs/framework/winforms/advanced/com-interop-by-displaying-a-windows-form-shadow.md)  
 Enthält ein Codebeispiel für die Verwendung der <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType>-Methode zum Ausführen eines Windows Forms in einer nicht verwalteten Anwendung.  
  
 [Vorgehensweise: Unterstützen von COM-Interop durch Anzeigen jedes Windows Forms in einem eigenen Thread](../../../../docs/framework/winforms/advanced/how-to-support-com-interop-by-displaying-each-windows-form-on-its-own-thread.md)  
 Enthält ein Codebeispiel für die Ausführung eines Windows Forms in einem eigenen Thread.  
  
 Siehe auch [Exemplarische Vorgehensweise: Unterstützen von COM-Interop durch das Anzeigen jedes Windows Forms in einem eigenen Thread](http://msdn.microsoft.com/library/ms233639\(v=vs.110\)).  
  
## <a name="reference"></a>Referenz  
 <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType>  
 Wird zum Erstellen eines separaten Threads für ein Windows Form verwendet.  
  
 <xref:System.Windows.Forms.Application.Run%2A?displayProperty=nameWithType>  
 Startet eine Nachrichtenschleife für einen Thread.  
  
 <xref:System.Windows.Forms.Control.Invoke%2A>  
 Marshallt Aufrufe von einer nicht verwalteten Anwendung für ein Formular.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Verfügbarmachen von .NET Framework-Komponenten in COM](../../../../docs/framework/interop/exposing-dotnet-components-to-com.md)  
 Bietet allgemeine Informationen zur Verwendung von .NET Framework-Typen in nicht verwalteten Anwendungen.
