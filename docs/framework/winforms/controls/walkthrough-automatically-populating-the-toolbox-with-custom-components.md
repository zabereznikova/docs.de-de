---
title: "Exemplarische Vorgehensweise: Automatisches Füllen der Toolbox mit benutzerdefinierten Komponenten"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IToolboxService interface
- Toolbox [Windows Forms], populating
- custom components [Windows Forms], adding to Toolbox
ms.assetid: 2fa1e3e8-6b9f-42b2-97c0-2be57444dba4
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6b60d4ee7908a5ed9dcb3393132ba7d0bd0a6cb5
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="walkthrough-automatically-populating-the-toolbox-with-custom-components"></a>Exemplarische Vorgehensweise: Automatisches Füllen der Toolbox mit benutzerdefinierten Komponenten
Wenn die Komponenten von einem Projekt in der gerade geöffneten Projektmappe definiert sind, werden sie automatisch in angezeigt der **Toolbox**, keine Aktion erforderlich. Sie können auch manuell Auffüllen der **Toolbox** mit den benutzerdefinierten Komponenten mithilfe der [Choose Toolbox Items Dialog Box (Visual Studio)](http://msdn.microsoft.com/library/bd07835f-18a8-433e-bccc-7141f65263bb), aber die **Toolbox** berücksichtigt der Elemente in der Projektmappe erstellen Sie Ausgaben mit den folgenden Merkmalen:  
  
-   Implementiert <xref:System.ComponentModel.IComponent>;  
  
-   Verfügt nicht über <xref:System.ComponentModel.ToolboxItemAttribute> festgelegt `false`;  
  
-   Verfügt nicht über <xref:System.ComponentModel.DesignTimeVisibleAttribute> festgelegt `false`.  
  
> [!NOTE]
>  Die **Toolbox** Verweis Ketten zu erkennen, werden nicht befolgt werden, damit keine Elemente angezeigt werden, die nicht von einem Projekt in der Projektmappe erstellt werden.  
  
 In dieser exemplarischen Vorgehensweise wird veranschaulicht, wie eine benutzerdefinierte Komponente automatisch in angezeigt wird der **Toolbox** , nachdem die Komponente erstellt wird. In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:  
  
-   Erstellen ein Windows Forms-Projekt.  
  
-   Erstellen eine benutzerdefinierte Komponente.  
  
-   Erstellen eine Instanz einer benutzerdefinierten Komponente.  
  
-   Entladen und erneutes Laden einer benutzerdefinierten Komponente.  
  
 Wenn Sie fertig sind, sehen Sie, den **Toolbox** wird aufgefüllt, mit einer Komponente, die Sie erstellt haben.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## <a name="creating-the-project"></a>Erstellen des Projekts  
 Im ersten Schritt wird das Projekt erstellt und das Formular eingerichtet.  
  
#### <a name="to-create-the-project"></a>So erstellen Sie das Projekt  
  
1.  Erstellen Sie ein Windows-basiertes Anwendungsprojekt mit dem Namen `ToolboxExample`.  
  
     Weitere Informationen finden Sie unter [How to: Create a Windows Application Project (Vorgehensweise: Erstellen eines neuen Windows Forms-Anwendungsprojekts)](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
2.  Fügen Sie dem Projekt eine neue Komponente hinzu. Rufen sie `DemoComponent`.  
  
     Weitere Informationen finden Sie unter [NIB: Vorgehensweise: Hinzufügen neuer Projektelemente](http://msdn.microsoft.com/library/63d3e16b-de6e-4bb5-a0e3-ecec762201ce).  
  
3.  Erstellen Sie das Projekt.  
  
4.  Aus der **Tools** Menü klicken Sie auf die **Optionen** Element. Klicken Sie auf **allgemeine** unter der **Windows Forms-Designer** Element und sicherstellen, dass die **AutoToolboxPopulate** Option wird festgelegt, um **"true"**.  
  
## <a name="creating-an-instance-of-a-custom-component"></a>Erstellen einer Instanz einer benutzerdefinierten Komponente  
 Der nächste Schritt besteht, eine Instanz der benutzerdefinierten Komponente auf dem Formular zu erstellen. Da die **Toolbox** automatisch die Konten für die neue Komponente, dies ist genauso einfach wie beliebige andere Komponenten oder Steuerelemente erstellen.  
  
#### <a name="to-create-an-instance-of-a-custom-component"></a>Zum Erstellen einer Instanz einer benutzerdefinierten Komponente  
  
1.  Öffnen Sie das Formular des Projekts in der **Forms-Designer**.  
  
2.  In der **Toolbox**, klicken Sie auf die neue Registerkarte **ToolboxExample-Komponenten**.  
  
     Sobald Sie auf die Registerkarte "klicken, sehen Sie **DemoComponent**.  
  
    > [!NOTE]
    >  Aus Leistungsgründen Komponenten im Bereich automatisch aufgefüllt, der die **Toolbox** benutzerdefinierte Bitmaps werden nicht angezeigt und die <xref:System.Drawing.ToolboxBitmapAttribute> wird nicht unterstützt. Zum Anzeigen eines Symbols für eine benutzerdefinierte Komponente in der **Toolbox**, verwenden Sie die **Toolboxelemente auswählen** (Dialogfeld), um die Komponente zu laden.  
  
3.  Ziehen Sie die Komponente auf dem Formular aus.  
  
     Eine Instanz der Komponente erstellt und hinzugefügt werden, um die **Komponentenleiste**.  
  
## <a name="unloading-and-reloading-a-custom-component"></a>Entladen und erneutes Laden einer benutzerdefinierten Komponente  
 Die **Toolbox** berücksichtigt die Komponenten in jedem geladenen Projekt entspricht, und bei einem Projekt entladen wurde, entfernen Sie Verweise auf Komponenten des Projekts.  
  
#### <a name="to-experiment-with-the-effect-on-the-toolbox-of-unloading-and-reloading-components"></a>Experimentieren Sie mit dem Effekt in der Toolbox des Entladens und erneuten Laden von Komponenten  
  
1.  Entladen Sie das Projekt aus der Projektmappe.  
  
     Weitere Informationen zu Projekte entladen, finden Sie unter [NIB: Gewusst: entladen und erneutes Laden von Projekten](http://msdn.microsoft.com/library/abc0155b-8fcb-4ffc-95b6-698518a7100b). Wenn Sie aufgefordert werden, speichern, wählen Sie **Ja**.  
  
2.  Fügen Sie einen neuen **Windows-Anwendung** Projekt der Projektmappe. Öffnen Sie das Formular in der **Designer**.  
  
     Die **ToolboxExample-Komponenten** Registerkarte aus dem vorherigen Projekt ist nicht mehr vorhanden.  
  
3.  Zum erneuten Laden der `ToolboxExample` Projekt.  
  
     Die **ToolboxExample-Komponenten** Registerkarte jetzt wird erneut angezeigt.  
  
## <a name="next-steps"></a>Nächste Schritte  
 Diese exemplarische Vorgehensweise veranschaulicht, die die **Toolbox** berücksichtigt Komponenten eines Projekts, aber die **Toolbox** ist auch Steuerelemente. Experimentieren Sie eigene benutzerdefinierte Steuerelemente durch Hinzufügen und entfernen Projekte in der Projektmappe aus.  
  
## <a name="see-also"></a>Siehe auch  
 [Allgemein, Windows Forms-Designer, Optionen (Dialogfeld)](http://msdn.microsoft.com/library/8dd170af-72f0-4212-b04b-034ceee92834)  
 [Vorgehensweise: Ändern von Registerkarten der Toolbox](http://msdn.microsoft.com/library/21285050-cadd-455a-b1f5-a2289a89c4db)  
 [Dialogfeld „Toolboxelemente auswählen“ (Visual Studio)](http://msdn.microsoft.com/library/bd07835f-18a8-433e-bccc-7141f65263bb)  
 [Einfügen von Steuerelementen in Windows Forms](../../../../docs/framework/winforms/controls/putting-controls-on-windows-forms.md)
