---
title: "Gewusst wie: Binden von Windows Forms-Steuerelementen an die BindingSource-Komponente mithilfe des Designers | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "BindingSource-Komponente [Windows Forms], Binden von Steuerelementen"
  - "Steuerelemente [Windows Forms], Bindung"
  - "Datenbindung, BindingSource-Komponente"
ms.assetid: 391ae170-de5c-40f8-8233-91cb2ee4683a
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# Gewusst wie: Binden von Windows Forms-Steuerelementen an die BindingSource-Komponente mithilfe des Designers
Nachdem Sie dem Formular Steuerelemente hinzugefügt und die Benutzeroberfläche für die Anwendung bestimmt haben, können Sie die Steuerelemente an eine Datenquelle binden, damit die Benutzer zur Laufzeit anwendungsspezifische Daten ändern und speichern können.  
  
 Zum Binden eines oder mehrerer Steuerelemente in Windows Forms empfiehlt sich die Verwendung des <xref:System.Windows.Forms.BindingSource>\-Steuerelements als Brücke zwischen den Steuerelementen auf dem Formular und der Datenquelle.  
  
 Ein oder mehrere Steuerelemente in einem Formular können an Daten gebunden sein. In der folgenden Prozedur ist ein <xref:System.Windows.Forms.TextBox>\-Steuerelement an eine Datenquelle gebunden.  
  
 Zur Ausführung der Prozedur wird davon ausgegangen, dass Sie an eine von einer Datenbank abgeleitete Datenquelle binden.  Weitere Informationen zum Erstellen von Datenquellen aus anderen Datenspeichern finden Sie unter [Übersicht über Datenquellen](../Topic/Add%20new%20data%20sources.md).  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.  Wählen Sie im Menü **Extras** die Option **Einstellungen importieren und exportieren** aus, um die Einstellungen zu ändern.  Weitere Informationen finden Sie unter [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/de-de/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### So binden Sie ein Steuerelement zur Entwurfszeit  
  
1.  Ziehen Sie ein <xref:System.Windows.Forms.TextBox>\-Steuerelement in das Formular.  
  
2.  Gehen Sie im **Eigenschaftenfenster** wie folgt vor:  
  
    1.  Erweitern Sie den **\(DataBindings\)**\-Knoten.  
  
    2.  Klicken Sie auf den Pfeil neben der <xref:System.Windows.Forms.TextBox.Text%2A>\-Eigenschaft.  
  
         Der **DataSource**\-UI\-Typ\-Editor wird geöffnet.  
  
         Wenn für das Projekt oder das Formular zuvor eine Datenquelle konfiguriert wurde, wird diese angezeigt.  
  
3.  Klicken Sie auf **Projektdatenquelle hinzufügen**, um eine Verbindung zu Daten herzustellen und eine Datenquelle zu erstellen.  
  
4.  Klicken Sie auf der Willkommensseite im **Assistent zum Konfigurieren von Datenquellen** auf **Weiter**.  
  
5.  Wählen Sie auf der Seite **Datenquellentyp auswählen** die Option **Datenbank** aus.  
  
6.  Wählen Sie auf der Seite **Wählen Sie Ihre Datenverbindung aus** eine Datenverbindung aus der Liste der verfügbaren Verbindungen aus.  Wenn die gewünschte Datenverbindung nicht verfügbar ist, wählen Sie **Neue Verbindung** aus, um eine neue Datenverbindung zu erstellen.  
  
7.  Wählen Sie **Ja, Verbindung speichern** aus, um die Verbindungszeichenfolge in der Anwendungskonfigurationsdatei zu speichern.  
  
8.  Wählen Sie die Datenbankobjekte aus, die in die Anwendung eingefügt werden sollen.  In diesem Fall wählen Sie ein Feld in einer Tabelle aus, das <xref:System.Windows.Forms.TextBox> anzeigen soll.  
  
9. Ersetzen Sie den Standarddatasetnamen, falls gewünscht.  
  
10. Klicken Sie auf **Fertig stellen**.  
  
11. Klicken Sie im **Eigenschaftenfenster** erneut auf den Pfeil neben der <xref:System.Windows.Forms.TextBox.Text%2A>\-Eigenschaft.  Wählen Sie im **DataSource**\-UI\-Typ\-Editor den Namen des Felds aus, an das <xref:System.Windows.Forms.TextBox> gebunden werden soll.  
  
     Der **DataSource**\-UI\-Typ\-Editor wird geschlossen, und das Dataset, die<xref:System.Windows.Forms.BindingSource> und der Tabellenadapter für die Datenverbindung werden dem Formular hinzugefügt.  
  
## Siehe auch  
 <xref:System.Windows.Forms.BindingSource>   
 <xref:System.Windows.Forms.BindingNavigator>   
 [Übersicht über Datenquellen](../Topic/Add%20new%20data%20sources.md)   
 [Datenquellenfenster](../Topic/Data%20Sources%20Window.md)