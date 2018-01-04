---
title: 'Gewusst wie: Binden von Windows Forms-Steuerelementen an die BindingSource-Komponente mithilfe des Designers'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- controls [Windows Forms], binding
- BindingSource component [Windows Forms], binding controls
- data binding [Windows Forms], BindingSource component
ms.assetid: 391ae170-de5c-40f8-8233-91cb2ee4683a
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 73b397d750d3883bf7613756889726a52e1233cd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-bind-windows-forms-controls-with-the-bindingsource-component-using-the-designer"></a>Gewusst wie: Binden von Windows Forms-Steuerelementen an die BindingSource-Komponente mithilfe des Designers
Nachdem Sie dem Formular Steuerelemente hinzugefügt und bestimmt die Benutzeroberfläche für Ihre Anwendung haben, können Sie die Steuerelemente an eine Datenquelle binden, sodass zur Laufzeit können Benutzer ändern und Speichern von Daten im Zusammenhang mit der Anwendung.  
  
 Binden ein Steuerelement oder eine Reihe von Steuerelementen in Windows Forms am einfachsten erfolgt mithilfe der <xref:System.Windows.Forms.BindingSource> Steuerelement als Brücke zwischen den Steuerelementen im Formular und die Datenquelle.  
  
 Ein oder mehrere Steuerelemente in einem Formular können an Daten gebunden werden. Im folgenden Verfahren ein <xref:System.Windows.Forms.TextBox> Steuerelement an eine Datenquelle gebunden ist.  
  
 Um den Vorgang abzuschließen, wird davon ausgegangen, dass Sie die Bindung mit einer Datenquelle abgeleitet, die aus einer Datenbank an. Weitere Informationen zum Erstellen von Datenquellen aus anderen Datenspeichern finden Sie unter [neue Datenquellen hinzufügen](/visualstudio/data-tools/add-new-data-sources).  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-bind-a-control-at-design-time"></a>Zum Binden eines Steuerelements zur Entwurfszeit  
  
1.  Ziehen Sie ein <xref:System.Windows.Forms.TextBox> Steuerelement an das Formular.  
  
2.  In der **Eigenschaften** Fenster:  
  
    1.  Erweitern Sie die **(DataBindings)** Knoten.  
  
    2.  Klicken Sie auf den Pfeil neben der <xref:System.Windows.Forms.TextBox.Text%2A> Eigenschaft.  
  
         Die **DataSource** UI-Typ-Editor wird geöffnet.  
  
         Wenn eine Datenquelle bereits für das Projekt oder Formular konfiguriert wurde, wird Sie angezeigt.  
  
3.  Klicken Sie auf **Projektdatenquelle hinzufügen**, um die Daten zu verbinden und die Datenquelle zu erzeugen.  
  
4.  Klicken Sie auf der Startseite des **Assistenten zum Konfigurieren von Datenquellen** auf **Weiter**.  
  
5.  Auf der **wählen Sie einen Datenquellentyp** Seite **Datenbank**.  
  
6.  Auf der **wählen Sie Ihre Datenverbindung** Seite anzuzeigen, wählen Sie eine Datenverbindung aus der Liste der verfügbaren Verbindungen. Wenn die gewünschte Datenverbindung nicht verfügbar Wählen ist **neue Verbindung** um eine neue Datenverbindung zu erstellen.  
  
7.  Wählen Sie **Ja, Verbindung speichern** so speichern die Verbindungszeichenfolge in der Anwendungskonfigurationsdatei.  
  
8.  Wählen Sie die Datenbankobjekte, die in die Anwendung gebracht werden sollen. In diesem Fall wählen Sie ein Feld in einer Tabelle, die Sie möchten die <xref:System.Windows.Forms.TextBox> angezeigt.  
  
9. Ersetzen Sie den Standardnamen des Datasets falls gewünscht.  
  
10. Klicken Sie auf **Fertig stellen**.  
  
11. In der **Eigenschaften** Fenster, klicken Sie auf den Pfeil neben der <xref:System.Windows.Forms.TextBox.Text%2A> Eigenschaft erneut aus. In der **DataSource** UI-Typ-Editor, wählen Sie den Namen des Felds, das Binden der <xref:System.Windows.Forms.TextBox> an.  
  
     Die **DataSource** UI-Typ Editor geschlossen wird und das Dataset <xref:System.Windows.Forms.BindingSource> und Tabellenadapters spezifische Datenverbindung zum Formular hinzugefügt werden.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.BindingSource>  
 <xref:System.Windows.Forms.BindingNavigator>  
 [Neue Datenquelle hinzufügen](/visualstudio/data-tools/add-new-data-sources)  
 [Datenquellenfenster](http://msdn.microsoft.com/library/0d20f699-cc95-45b3-8ecb-c7edf1f67992)
