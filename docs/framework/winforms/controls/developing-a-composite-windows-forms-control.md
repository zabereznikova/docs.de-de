---
title: "Entwickeln eines zusammengesetzten Windows Forms-Steuerelements"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- custom controls [Windows Forms], composite controls
- composite controls [Windows Forms]
- composite controls [Windows Forms], Windows Forms
- controls [Windows Forms], composite
ms.assetid: d086f2a3-baa3-4e09-b40c-a5bb3cfc51a6
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: da180f888031aace892efc770184be53e9341047
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="developing-a-composite-windows-forms-control"></a>Entwickeln eines zusammengesetzten Windows Forms-Steuerelements
Sie können ein zusammengesetztes Windows Forms-Steuerelement entwickeln, indem Sie andere Windows Forms-Steuerelemente kombinieren. Zusammengesetzte Steuerelemente, die davon Herleiten <xref:System.Web.UI.UserControl> werden als Benutzersteuerelemente bezeichnet. Die Basisklasse, <xref:System.Windows.Forms.UserControl>, ermöglicht Tastaturrouting für die untergeordneten Steuerelemente und stellt damit sicher, dass untergeordnete Steuerelemente den Fokus erhalten können. Ein Beispiel für ein Benutzersteuerelement, finden Sie unter der <xref:System.Windows.Forms.UserControl> -Beispiel in [wie: Anwenden von Attributen auf Windows Forms-Steuerelementen](../../../../docs/framework/winforms/controls/how-to-apply-attributes-in-windows-forms-controls.md).  
  
 Der Windows Forms-Designer in [!INCLUDE[vsprvsext](../../../../includes/vsprvsext-md.md)] stellt umfassende Entwurfszeitunterstützung für die Erstellung von Benutzersteuerelementen bereit.  
  
-   [Gewusst wie: Anzeigen eines Steuerelements im Dialogfeld „Toolboxelemente auswählen“](http://msdn.microsoft.com/library/9yxtkx75\(v=vs.110\))  
  
-   [Exemplarische Vorgehensweise: Serialisieren der Auflistungen von Standardtypen mit dem DesignerSerializationVisibilityAttribute](http://msdn.microsoft.com/library/ms171731\(v=vs.110\))  
  
-   [Exemplarische Vorgehensweise: Vererben von einem Windows Forms-Steuerelement mit Visual C#](http://msdn.microsoft.com/en-us/09476da0-8d4c-4a4c-b969-649519dfb438)  
  
-   [Gewusst wie: Bereitstellen einer Toolboxbitmap für ein Steuerelement](http://msdn.microsoft.com/library/4wk1wc0a\(v=vs.110\))  
  
-   [Vorgehensweise: Erben von vorhandenen Windows Forms-Steuerelementen](http://msdn.microsoft.com/library/7h62478z\(v=vs.110\))  
  
-   [Exemplarische Vorgehensweise: Debuggen von benutzerdefinierten Windows Forms-Steuerelementen zur Entwurfszeit](http://msdn.microsoft.com/library/5ytx0z24\(v=vs.110\))  
  
-   [Vorgehensweise: Erben von der Control-Klasse](http://msdn.microsoft.com/library/skcysbt2\(v=vs.110\))  
  
-   [Vorgehensweise: Testen des Laufzeitverhaltens eines UserControl](http://msdn.microsoft.com/library/ms171738\(v=vs.110\))  
  
-   [Vorgehensweise: Ausrichten eines Steuerelements an den Rändern eines Formulars zur Entwurfszeit](http://msdn.microsoft.com/library/1fxyb15b\(v=vs.110\))  
  
-   [Vorgehensweise: Erben von der UserControl-Klasse](http://msdn.microsoft.com/library/00ctb4z0\(v=vs.110\))  
  
-   [Vorgehensweise: Erstellen von Steuerelementen für Windows Forms](http://msdn.microsoft.com/library/bs3yhkh7\(v=vs.110\))  
  
-   [Vorgehensweise: Erstellen von zusammengesetzten Steuerelementen](http://msdn.microsoft.com/library/3sf86w5h\(v=vs.110\))  
  
-   [Exemplarische Vorgehensweise: Erstellen eines zusammengesetzten Steuerelements mit Visual Basic](http://msdn.microsoft.com/library/c316f119\(v=vs.110\))  
  
-   [Exemplarische Vorgehensweise: Erstellen eines zusammengesetzten Steuerelements mit Visual C#](http://msdn.microsoft.com/en-us/f88481a8-c746-4a36-9479-374ce5f2e91f)  
  
-   [Exemplarische Vorgehensweise: Vererben eines Windows Forms-Steuerelements mit Visual Basic](http://msdn.microsoft.com/library/w2a8y03d\(v=vs.110\))  
  
-   [Vorgehensweise: Erstellen eines Windows Forms-Steuerelements, das Entwurfszeitfeatures nutzt](http://msdn.microsoft.com/library/307hck25\(v=vs.110\))  
  
-   [Vorgehensweise: Erstellen eines Windows Forms-Steuerelements, das Entwurfszeitfeatures nutzt](http://msdn.microsoft.com/library/307hck25\(v=vs.120\))  
  
## <a name="see-also"></a>Siehe auch  
 [Vorgehensweise: Anwenden von Attributen auf Windows Forms-Steuerelemente](../../../../docs/framework/winforms/controls/how-to-apply-attributes-in-windows-forms-controls.md)  
 [Entwickeln benutzerdefinierter Windows Forms-Steuerelemente mit .NET Framework](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)  
 [Varieties of Custom Controls (Vielfalt benutzerdefinierter Steuerelemente)](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)
