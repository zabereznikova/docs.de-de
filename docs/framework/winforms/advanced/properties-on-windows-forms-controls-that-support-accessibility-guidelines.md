---
title: "Eigenschaften f&#252;r Windows Forms-Steuerelemente, die Richtlinien f&#252;r Eingabehilfen unterst&#252;tzen | Microsoft Docs"
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
  - "Barrierefreiheit, Windows Forms-Steuerelementeigenschaften"
  - "Windows Forms, Eingabehilfeeigenschaften von Steuerelementen"
ms.assetid: ad3567a6-313b-4708-9e15-f487a831f049
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# Eigenschaften f&#252;r Windows Forms-Steuerelemente, die Richtlinien f&#252;r Eingabehilfen unterst&#252;tzen
Die Steuerelemente in der Standardtoolbox für Windows Forms unterstützen zahlreiche Richtlinien für Barrierefreiheit, einschließlich der Anzeige des Tastaturfokus sowie der Bildschirmelemente.  
  
## Planen von Barrierefreiheit  
 Die Eigenschaften der Steuerelemente können, wie aus der folgenden Tabelle ersichtlich, zur Unterstützung weiterer Richtlinien für Barrierefreiheit verwendet werden.  Sie sollten zusätzlich Menüs verwenden, um den Zugriff auf Programmfeatures zu ermöglichen.  
  
|Steuerelementeigenschaft|Überlegungen zu Barrierefreiheit|  
|------------------------------|--------------------------------------|  
|AccessibleDescription|Die Beschreibung wird an Barrierefreiheit\-Hilfsmittel gemeldet, z. B. als Sprachausgabe.  Hilfstechnologien für die Barrierefreiheit sind spezielle Programme und Geräte, die Menschen mit Behinderungen die Verwendung des Computers erleichtern.|  
|AccessibleName|Der an die Barrierefreiheit\-Hilfsmittel gemeldete Name.|  
|AccessibleRole|Beschreibt die Verwendung des Elements in der Benutzeroberfläche.|  
|TabIndex|Erstellt einen logischen Navigationspfad über das Formular.  Bei Steuerelementen ohne systeminterne Bezeichnung, z. B. Textfeldern, muss die zugeordnete Bezeichnung dem Steuerelement in der Aktivierreihenfolge direkt vorangestellt wird.|  
|Text|Verwenden Sie ein kaufmännisches Und\-Zeichen \("&"\), um Zugriffstasten zu erstellen.  Die Verwendung von Zugriffstasten ist Teil der Bereitstellung des dokumentierten Tastaturzugriffs auf alle Features.|  
|Font Size|Wenn der Schriftgrad nicht angepasst werden kann, sollte er auf 10 Punkt oder größer gesetzt werden.  Nachdem der Schriftgrad des Formulars festgelegt ist, erhalten alle anschließend zum Formular hinzugefügten Steuerelemente dieselbe Größe.|  
|ForeColor|Wenn für diese Eigenschaft der Standardwert festgelegt ist, werden die Farbeinstellungen des Benutzers für das Formular verwendet.|  
|BackColor|Wenn für diese Eigenschaft der Standardwert festgelegt ist, werden die Farbeinstellungen des Benutzers für das Formular verwendet.|  
|BackgroundImage|Lassen Sie diese Eigenschaft zur besseren Lesbarkeit des Textes leer.|  
  
## Siehe auch  
 [Exemplarische Vorgehensweise: Erstellen von behindertengerechten Windows\-basierten Anwendungen](../../../../docs/framework/winforms/advanced/walkthrough-creating-an-accessible-windows-based-application.md)