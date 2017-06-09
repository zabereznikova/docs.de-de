---
title: "Gewusst wie: Erben von Formularen mithilfe des Dialogfelds &quot;Vererbungsauswahl&quot; | Microsoft Docs"
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
  - "Vererbung, Formulare"
  - "Vererbungsauswahl (Dialogfeld)"
  - "Geerbte Formulare, erstellen"
ms.assetid: 969b4c04-12aa-4297-93a2-0ae747447823
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Gewusst wie: Erben von Formularen mithilfe des Dialogfelds &quot;Vererbungsauswahl&quot;
Das Dialogfeld **Vererbungsauswahl** bietet die einfachste Möglichkeit, ein Formular oder ein anderes Objekt zu erben.  Mithilfe dieser Option können Sie die Vorteile von Codezeichenfolgen oder Benutzeroberflächen \(UI\) nutzen, die Sie bereits in anderen Projektmappen erstellt haben.  
  
> [!NOTE]
>  Damit die Formularvererbung vom Dialogfeld **Vererbungsauswahl** unterstützt wird, muss das Projekt mit dem jeweiligen Formular in eine ausführbare Datei oder DLL integriert werden.  Wählen Sie zum Erstellen des Projekts im Menü **Erstellen** die Option **Projektmappe erstellen** aus.  
>   
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.  Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren**, um die Einstellungen zu ändern.  Weitere Informationen finden Sie unter [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/de-de/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### So erstellen Sie ein von einem vorhandenen Formular geerbtes Windows Form mithilfe der Vererbungsauswahl  
  
1.  Wählen Sie im Menü **Projekt** den Punkt **Windows Form hinzufügen**.  
  
     Das Dialogfeld **Neues Element hinzufügen** wird angezeigt.  
  
2.  Wählen Sie die Vorlage **Geerbtes Formular** aus, und weisen Sie ihr im Feld **Name** einen Namen zu.  Klicken Sie auf die Schaltfläche **Hinzufügen**, um fortzufahren.  
  
     Das Dialogfeld **Vererbungsauswahl** wird geöffnet.  Wenn das aktuelle Projekt bereits Formulare enthält, werden diese im Dialogfeld **Vererbungsauswahl** angezeigt.  
  
3.  Um von einem Formular in einer anderen Assembly zu erben, klicken Sie auf die Schaltfläche **Durchsuchen**.  
  
4.  Navigieren Sie im Dialogfeld **Eine Datei auswählen, die eine Komponente für die Vererbung enthält** zu dem Projekt, das das gewünschte Formular oder Modul enthält.  
  
5.  Klicken Sie auf den Namen der EXE\- oder DLL\-Datei, um sie zu markieren, und klicken Sie dann auf die Schaltfläche **Öffnen**.  
  
     Daraufhin kehren Sie zum Dialogfeld **Vererbungsauswahl** zurück, in dem jetzt die Komponente zusammen mit dem Projekt, in dem sie gespeichert ist, aufgelistet wird.  
  
6.  Wählen Sie die Komponente aus.  
  
     Die Komponente wird dem Projekt im **Projektmappen\-Explorer** hinzugefügt.  Falls die Komponente über eine Benutzeroberfläche verfügt, werden die Steuerelemente, die Bestandteil des geerbten Formulars sind, mit einem Symbol \(![VisualBasicInheritanceSymbol&#45;Bildschirmabbildung](../../../../docs/framework/winforms/advanced/media/vbinheritanceglyph.png "vbInheritanceGlyph")\) gekennzeichnet. Sobald Sie eines dieser Steuerelemente auswählen, können Sie am Rahmen erkennen, welche Sicherheitsebene das Steuerelement im Formular der übergeordneten Klasse besitzt.  In der folgenden Tabelle sind die Verhaltensweisen aufgeführt, die den verschiedenen Sicherheitsebenen entsprechen.  
  
    |Sicherheitsebene des Steuerelements|Mögliche Interaktion mit geerbtem Formular im Designer und Code\-Editor|  
    |-----------------------------------------|-----------------------------------------------------------------------------|  
    |Public|Standardrahmen mit Ziehpunkten: Das Steuerelement kann vergrößert, verkleinert und verschoben werden.  Auf das Steuerelement kann intern durch die Klasse, durch die es deklariert wird, und extern durch andere Klassen zugegriffen werden.|  
    |Protected|Standardrahmen mit Ziehpunkten: Das Steuerelement kann vergrößert, verkleinert und verschoben werden.  Auf das Steuerelement kann intern durch die Klasse, durch die es deklariert wird, und durch alle Klassen, die von der übergeordneten Klasse erben, nicht jedoch durch externe Klassen zugegriffen werden.|  
    |Protected Internal \(Protected Friend in Visual Basic\)|Standardrahmen mit Ziehpunkten: Das Steuerelement kann vergrößert, verkleinert und verschoben werden.  Auf das Steuerelement kann intern durch die Klasse, durch die es deklariert wird, durch alle Klassen, die von der übergeordneten Klasse erben, sowie durch andere Member der Assembly, die es enthält, zugegriffen werden.|  
    |Internal \(Friend in Visual Basic\)|Standardrahmen ohne Ziehpunkte: Das Steuerelement wird im Formular angezeigt, und seine Eigenschaften sind im **Eigenschaftenfenster** sichtbar.  Sämtliche Merkmale des Steuerelements werden jedoch als schreibgeschützt betrachtet.  Das Steuerelement kann nicht verschoben und Größe oder Eigenschaften können nicht geändert werden.  Wenn es sich bei dem Steuerelement um einen Container für andere Steuerelemente \(z. B. um ein Gruppenfeld\) handelt, können keine neuen Steuerelemente hinzugefügt und keine vorhandenen Steuerelemente entfernt werden. Dies gilt auch dann, wenn diese Steuerelemente die "Public"\-Eigenschaft besitzen.  Auf das Steuerelement können nur andere Member der Assembly zugreifen, die es enthält.|  
    |Private|Standardrahmen ohne Ziehpunkte: Das Steuerelement wird im Formular angezeigt, und seine Eigenschaften sind im **Eigenschaftenfenster** sichtbar.  Sämtliche Merkmale des Steuerelements werden jedoch als schreibgeschützt betrachtet.  Das Steuerelement kann nicht verschoben und Größe oder Eigenschaften können nicht geändert werden.  Wenn es sich bei dem Steuerelement um einen Container für andere Steuerelemente \(z. B. um ein Gruppenfeld\) handelt, können keine neuen Steuerelemente hinzugefügt und keine vorhandenen Steuerelemente entfernt werden. Dies gilt auch dann, wenn diese Steuerelemente die "Public"\-Eigenschaft besitzen.  Auf das Steuerelement kann nur durch die Klasse zugegriffen werden, durch die es deklariert wird.|  
  
     Informationen zum Ändern der Darstellung eines Basisformulars finden Sie unter [Auswirkungen beim Ändern der Darstellung von Basisformularen](../../../../docs/framework/winforms/advanced/effects-of-modifying-base-form-appearance.md).  
  
    > [!NOTE]
    >  Wenn Sie geerbte Steuerelemente und Komponenten mit standardmäßigen Steuerelementen und Komponenten in Windows Forms kombinieren, treten möglicherweise Konflikte hinsichtlich der Z\-Reihenfolge auf.  Sie können dieses Problem lösen, indem Sie die Z\-Reihenfolge ändern. Zeigen Sie hierzu im Menü **Format** auf **Reihenfolge**, und klicken Sie dann auf **In den Vordergrund** oder **In den Hintergrund**.  Weitere Informationen zur Z\-Reihenfolge von Steuerelementen finden Sie unter [Gewusst wie: Überlagern von Objekten in Windows Forms](../../../../docs/framework/winforms/controls/how-to-layer-objects-on-windows-forms.md).  
  
## Siehe auch  
 [Inherits Statement](../../../../ocs/visual-basic/language-reference/statements/inherits-statement.md)   
 [Verwenden](../Topic/using%20\(C%23%20Reference\).md)   
 [Auswirkungen beim Ändern der Darstellung von Basisformularen](../../../../docs/framework/winforms/advanced/effects-of-modifying-base-form-appearance.md)   
 [Visuelle Vererbung in Windows Forms](../../../../docs/framework/winforms/advanced/windows-forms-visual-inheritance.md)