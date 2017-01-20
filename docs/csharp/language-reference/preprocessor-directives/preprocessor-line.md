---
title: "#line (C#-Referenz) | Microsoft Docs"
ms.custom: ""
ms.date: "01/05/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "#line"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "#line-Direktive [C#]"
ms.assetid: 6439e525-5dd5-4acb-b8ea-efabb32ff95b
caps.latest.revision: 13
caps.handback.revision: 13
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# #line (C#-Referenz)
Mit `#line` können die Zeilennummer des Compilers und optional der Dateiname, die für Fehler und Warnungen ausgegeben werden, geändert werden.  Dieses Beispiel zeigt, wie zwei Warnungen mit zugeordneten Zeilennummern in einem Fehlerbericht angezeigt werden.  Die `#line 200`\-Direktive erzwingt \(trotz der Standardeinstellung von \#7\) eine Festlegung der Zeilennummer auf 200, und der Dateiname wird bis zur folgenden \#line\-Direktive als "Special" gemeldet.  Die \#line default\-Direktive setzt die Zeilennummerierung auf das Standardverfahren zurück, das die Zeilen zählt, die von der vorherigen Direktive neu nummeriert wurden.  
  
```  
class MainClass  
{  
    static void Main()  
    {  
#line 200 "Special"  
        int i;    // CS0168 on line 200  
        int j;    // CS0168 on line 201  
#line default  
        char c;   // CS0168 on line 9  
        float f;  // CS0168 on line 10  
#line hidden // numbering not affected  
        string s;   
        double d; // CS0168 on line 13  
    }  
}  
```  
  
## Hinweise  
 Die `#line`\-Direktive kann während des Buildprozesses in einem automatisierten Zwischenschritt verwendet werden.  Wenn z. B. Zeilen aus der ursprünglichen Quellcodedatei entfernt wurden, der Compiler die Ausgabe aber weiterhin basierend auf der ursprünglichen Zeilennummerierung der Datei generieren soll, können Zeilen entfernt und die ursprüngliche Zeilennummerierung dann mit `#line` simuliert werden.  
  
 Durch die `#line hidden`\-Direktive werden die aufeinander folgenden Zeilen vor dem Debugger verborgen, sodass alle Zeilen zwischen einer `#line hidden`\-Direktive und der nächsten `#line`\-Direktive \(sofern es sich nicht um eine weitere `#line hidden`\-Direktive handelt\) übergangen werden, wenn der Entwickler den Code schrittweise durchgeht.  Anhand dieser Option kann ASP.NET auch die Möglichkeit eingeräumt werden, zwischen benutzerdefiniertem und computergeneriertem Code zu unterscheiden.  Obwohl es sich bei ASP.NET um den Hauptnutzer dieses Features handelt, ist davon auszugehen, dass es von mehreren Programmen zur Quellcodegenerierung verwendet wird.  
  
 Eine `#line hidden`\-Direktive hat keinen Einfluss auf Dateinamen oder Zeilennummern in Fehlerberichten.  Wenn ein Fehler also in einem verborgenen Block auftritt, gibt der Compiler den aktuellen Dateinamen und die Zeilennummer des Fehlers an.  
  
 Die `#line filename`\-Direktive gibt den Dateiname an, der in der Ausgabe des Compilers angezeigt werden soll.  Standardmäßig wird der tatsächliche Name der Quellcodedatei verwendet.  Der Dateiname muss in doppelten Anführungszeichen \(""\) angegeben werden und mit einer Zeilennummer beginnen.  
  
 Eine Quellcodedatei kann eine beliebige Anzahl von `#line`\-Direktiven enthalten.  
  
## Beispiel 1  
 Im folgenden Beispiel wird veranschaulicht, wie der Debugger die verborgenen Codezeilen ignoriert.  Beim Ausführen dieses Beispiels werden drei Textzeilen angezeigt.  Wenn Sie jedoch, wie im Beispiel, einen Haltepunkt festlegen und den Code mit F10 schrittweise durchlaufen, werden Sie feststellen, dass die verborgene Zeile vom Debugger ignoriert wird.  Die Zeile wird vom Debugger auch ignoriert, wenn Sie an der verborgenen Zeile einen Haltepunkt setzen.  
  
```  
// preprocessor_linehidden.cs  
using System;  
class MainClass   
{  
    static void Main()   
    {  
        Console.WriteLine("Normal line #1."); // Set break point here.  
#line hidden  
        Console.WriteLine("Hidden line.");  
#line default  
        Console.WriteLine("Normal line #2.");  
    }  
}  
```  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C\#\-Präprozessordirektiven](../../../csharp/language-reference/preprocessor-directives/index.md)