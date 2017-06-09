---
title: "Gewusst wie: Anzeigen eines Steuerelements im Dialogfeld &quot;Toolboxelemente ausw&#228;hlen&quot; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Globaler Assemblycache, Toolboxelemente auswählen (Dialogfeld)"
  - "AssemblyFoldersEx, Toolboxelemente auswählen (Dialogfeld)"
  - "Steuerelemente, Anzeigen im Dialogfeld „Toolboxelemente auswählen“"
  - "Assemblyordnerregistrierung, Toolboxelemente auswählen (Dialogfeld)"
  - "Toolboxelemente auswählen (Dialogfeld), Anzeigesteuerelement"
ms.assetid: 01ef6eba-d044-40f0-951d-78eff7ebd9a9
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Gewusst wie: Anzeigen eines Steuerelements im Dialogfeld &quot;Toolboxelemente ausw&#228;hlen&quot;
Beim Entwickeln und Verteilen von Steuerelementen können Sie die Steuerelemente im Dialogfeld **Toolboxelemente auswählen** verwenden; das Dialogfeld wird angezeigt, wenn Sie mit der rechten Maustaste auf **Toolbox** klicken und **Elemente auswählen** auswählen.  Sie können Ihr Steuerelement in diesem Dialogfeld anzeigen, indem Sie das AssemblyFoldersEx\-Registrierungsverfahren verwenden.  
  
### So zeigen Sie Ihr Steuerelement im Dialogfeld Toolboxelemente auswählen an  
  
-   Installieren Sie die Steuerelementassembly im globalen Assemblycache.  Weitere Informationen finden Sie unter [Gewusst wie: Installieren einer Assembly in den globalen Assemblycache](../../../../docs/framework/app-domains/how-to-install-an-assembly-into-the-gac.md).  
  
     \- oder \-  
  
-   Registrieren Sie das Steuerelement und die zugehörigen Entwurfszeitassemblys mit der AssemblyFoldersEx\-Registrierungsprozedur.  AssemblyFoldersEx ist ein Registrierungsspeicherort, an dem Drittanbieter Pfade für jede Version des Frameworks, das sie unterstützen, speichern.  Bei der Entwurfszeitauflösung kann an diesem Registrierungsspeicherort nach Referenzassemblys gesucht werden.  Das Registrierungsskript kann die Steuerelemente angeben, die in der Toolbox angezeigt werden sollen.  Weitere Informationen finden Sie unter [Bereitstellen eines benutzerdefinierten Steuerelements und von Entwurfszeitassemblys](http://msdn.microsoft.com/de-de/96158eb0-b691-4ae1-9e7b-3c65a1b798cb).  
  
## Siehe auch  
 [Choose Toolbox Items Dialog Box \(Visual Studio\)](http://msdn.microsoft.com/de-de/bd07835f-18a8-433e-bccc-7141f65263bb)   
 [Bereitstellen eines benutzerdefinierten Steuerelements und von Entwurfszeitassemblys](http://msdn.microsoft.com/de-de/96158eb0-b691-4ae1-9e7b-3c65a1b798cb)   
 [Entwickeln von Windows Forms\-Steuerelementen zur Entwurfszeit](../../../../docs/framework/winforms/controls/developing-windows-forms-controls-at-design-time.md)   
 [Gewusst wie: Installieren einer Assembly in den globalen Assemblycache](../../../../docs/framework/app-domains/how-to-install-an-assembly-into-the-gac.md)   
 [Exemplarische Vorgehensweise: Automatisches Füllen der Toolbox mit benutzerdefinierten Komponenten](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md)