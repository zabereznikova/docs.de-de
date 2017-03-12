---
title: "/nowarn (C# Compiler Options) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "/nowarn"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "nowarn compiler option [C#]"
  - "/nowarn compiler option [C#]"
  - "-nowarn compiler option [C#]"
ms.assetid: 6dcbc5e8-ae67-4566-9df3-f63cfdd9c4e4
caps.latest.revision: 24
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 24
---
# /nowarn (C# Compiler Options)
Mit der Option **\/nowarn** wird das Anzeigen von einer oder mehreren Warnungen durch den Compiler unterdrückt.  Trennen Sie mehrere Warnungsnummern jeweils durch ein Komma voneinander.  
  
## Syntax  
  
```  
/nowarn:number1[,number2,...]  
```  
  
## Argumente  
 `number1`, `number2`  
 Warnungsnummern, die der Compiler unterdrücken soll.  
  
## Hinweise  
 Geben Sie lediglich den numerischen Teil des Warnungsbezeichners an.  Wenn Sie beispielsweise CS0028 unterdrücken möchten, geben Sie `/nowarn:28` an.  
  
 Der Compiler ignoriert daraufhin ohne Angabe von Fehlernummern die an `/nowarn` übergebenen Warnungsnummern, die in früheren Versionen gültig waren, mittlerweile jedoch aus dem Compiler entfernt wurden.  CS0679 wurde im Compiler von Visual Studio .NET 2002 beispielsweise verwendet, anschließend jedoch entfernt.  
  
 Die folgenden Warnungen können nicht mit der Option `/nowarn` unterdrückt werden:  
  
-   Compilerwarnungen \(Ebene 1\) CS2002  
  
-   Compilerwarnungen \(Ebene 1\) CS2023  
  
-   Compilerwarnungen \(Ebene 1\) CS2029  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie die Seite **Eigenschaften** für das Projekt.  Ausführliche Informationen finden Sie unter [Seite "Erstellen", Projekt\-Designer \(C\#\)](/visual-studio/ide/reference/build-page-project-designer-csharp).  
  
2.  Klicken Sie auf die Eigenschaftenseite **Erstellen**.  
  
3.  Ändern Sie die Eigenschaft **Warnungen unterdrücken**.  
  
 Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.ProjectProperties3.DelaySign%2A>.  
  
## Siehe auch  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [Gewusst wie: Ändern von Projekteigenschaften und Konfigurationseinstellungen](http://msdn.microsoft.com/de-de/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)   
 [C\# Compiler Errors](../../../csharp/language-reference/compiler-messages/index.md)