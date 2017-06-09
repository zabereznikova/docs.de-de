---
title: "Anzeigen asiatischer Zeichen mit der ImeMode-Eigenschaft | Microsoft Docs"
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
  - "Asiatische Sprachen"
  - "Asiatische Sprachen, Anzeigen mit ImeMode"
  - "Chinesische Zeichen, Anzeigen mit ImeMode"
  - "Globalisierung [Windows Forms], Zeichensätze"
  - "IME-Modus"
  - "IMEMode-Eigenschaft"
  - "Eingabemethoden-Editor (IME), Modus"
  - "Internationale Anwendungen [Windows Forms], Zeichenanzeige"
  - "Internationale Zeichen"
  - "Japanische Zeichen, Anzeigen mit ImeMode"
  - "Koreanische Zeichen"
  - "Lokalisierung [Windows Forms], Zeichensätze"
ms.assetid: c60ae399-0dab-4f07-9dea-6dbfb15ec0ae
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# Anzeigen asiatischer Zeichen mit der ImeMode-Eigenschaft
Mit der <xref:System.Windows.Forms.Control.ImeMode%2A>\-Eigenschaft wird in Formularen und Steuerelementen ein bestimmter Modus für einen Eingabemethoden\-Editor \(Input Method Editor, IME\) erzwungen.  Der IME ist eine wichtige Komponente beim Schreiben von chinesischen, japanischen und koreanischen Skripts, da diese Schriftsysteme mehr Zeichen enthalten als für eine normale Tastatur codiert werden können.  Beispiel: In ein bestimmtes Textfeld sollen nur ASCII\-Zeichen eingetragen werden dürfen.  In diesem Fall legen Sie die <xref:System.Windows.Forms.Control.ImeMode%2A>\-Eigenschaft auf <xref:System.Windows.Forms.ImeMode> fest. Die Benutzer können in dieses Textfeld dann nur ASCII\-Zeichen eingeben.  Der Standardwert der <xref:System.Windows.Forms.Control.ImeMode%2A>\-Eigenschaft lautet <xref:System.Windows.Forms.ImeMode>, d. h. wenn Sie eine Eigenschaft für ein Formular festlegen, erben alle Steuerelemente des Formulars diese Einstellung.  Weitere Informationen finden Sie unter [Control.ImeMode\-Eigenschaft](frlrfSystemWindowsFormsControlClassImeModeTopic) und [ImeMode\-Enumeration](frlrfSystemWindowsFormsImeModeClassTopic).  
  
## Siehe auch  
 [Globalisieren von Windows Forms](../../../../docs/framework/winforms/advanced/globalizing-windows-forms.md)