---
title: "extern (C#-Referenz) | Microsoft Docs"
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
  - "extern_CSharpKeyword"
  - "extern"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "DllImport-Attribut"
  - "extern-Schlüsselwort [C#]"
ms.assetid: 9c3f02c4-51b8-4d80-9cb2-f2b6e1ae15c7
caps.latest.revision: 26
caps.handback.revision: 26
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# extern (C#-Referenz)
Der `extern`\-Modifizierer wird verwendet, um eine extern implementierte Methode zu deklarieren.  Der `extern`\-Modifizierer wird häufig mit dem `DllImport`\-Attribut verwendet, wenn Sie nicht verwalteten Code mit Interop\-Diensten aufrufen.  In diesem Fall muss die Methode auch als `static` deklariert werden, wie im folgenden Beispiel gezeigt:  
  
```  
[DllImport("avifil32.dll")]  
private static extern void AVIFileInit();  
```  
  
 Das `extern`\-Schlüsselwort kann ebenso einen externen Assemblyalias definieren. Dadurch wird es möglich, aus einer einzigen Assembly heraus auf unterschiedliche Versionen derselben Komponente zu verweisen.  Weitere Informationen finden Sie unter [extern\-Alias](../../../csharp/language-reference/keywords/extern-alias.md).  
  
 Der [abstract](../../../csharp/language-reference/keywords/abstract.md)\-Modifizierer und der `extern`\-Modifizierer dürfen nicht gleichzeitig auf demselben Member angewendet werden.  So bedeutet die Verwendung des `extern`\-Modifizierers, dass die Methode außerhalb des C\#\-Codes implementiert wird, während bei Verwendung des `abstract`\-Modifizierers die Methodenimplementierung nicht in der Klasse bereitgestellt wird.  
  
 Die Verwendung des extern\-Schlüsselworts ist in C\# eingeschränkter als in C\+\+.  Informationen zum Vergleichen des C\#\-Schlüsselworts mit dem C\+\+\-Schlüsselwort finden Sie unter "Using extern to Specify Linkage" in der C\+\+\-Sprachreferenz.  
  
## Beispiel  
 **Beispiel 1.** In diesem Beispiel empfängt das Programm eine Zeichenfolge vom Benutzer und zeigt sie in einem Meldungsfeld an.  Das Programm verwendet die `MessageBox`\-Methode, die von der User32.dll\-Bibliothek importiert wurde.  
  
 [!code-cs[csrefKeywordsModifiers#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/csrefKeywordsModifiers/csrefKeywordsModifiers.cs#8)]  
  
## Beispiel  
 **Beispiel 2.** Dieses Beispiel veranschaulicht ein C\#\-Programm, das eine C\-Bibliothek aufruft \(eine systemeigene DLL\).  
  
 1.  Erstellen Sie die folgende C\-Datei mit dem Namen `cmdll.c`:  
  
```  
// cmdll.c  
// Compile with: /LD  
int __declspec(dllexport) SampleMethod(int i)  
{  
   return i*10;  
}  
```  
  
## Beispiel  
 2.  Öffnen Sie ein Visual Studio x64 \(oder x32\) Native Tools\-Eingabeaufforderungsfenster im Visual Studio\-Installationsverzeichnis, und kompilieren Sie die `cmdll.c`\-Datei, indem Sie an der Eingabeaufforderung **cl \/LD cmdll.c** eingeben.  
  
 3.  Erstellen Sie im gleichen Verzeichnis die folgende C\#\-Datei mit dem Namen `cm.cs`:  
  
```  
// cm.cs  
using System;  
using System.Runtime.InteropServices;  
public class MainClass   
{  
   [DllImport("Cmdll.dll")]  
   public static extern int SampleMethod(int x);  
  
   static void Main()   
   {  
      Console.WriteLine("SampleMethod() returns {0}.", SampleMethod(5));  
   }  
}  
```  
  
## Beispiel  
 3.  Öffnen Sie ein Visual Studio x64 \(oder x32\) Native Tools\-Eingabeaufforderungsfenster im Visual Studio\-Installationsverzeichnis, und kompilieren Sie die `cm.cs`\-Datei, indem Sie Folgendes eingeben:  
  
> **csc cm.cs** \(für die x64\-Eingabeaufforderung\)   
>  – oder –  
> **csc \/platform:x86 cm.cs** \(für die x32\-Eingabeaufforderung\)  
  
 Dadurch wird die ausführbare Datei `cm.exe` erstellt.  
  
 4.  Führen Sie `cm.exe` aus.  Die `SampleMethod`\-Methode übergibt den Wert 5 an die DLL\-Datei, die den mit 10 multiplizierten Wert zurückgibt. Das Programm generiert die folgende Ausgabe:  
  
```  
SampleMethod() returns 50.  
```  
  
## C\#\-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Siehe auch  
 <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName>   
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C\#\-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)   
 [Modifizierer](../../../csharp/language-reference/keywords/modifiers.md)