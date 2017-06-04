---
title: "How to: Compile Conditionally with Trace and Debug | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "trace compiler options"
  - "trace statements"
  - "compiling source code, trace statements"
  - "tracing [.NET Framework], enabling or disabling"
  - "tracing [.NET Framework], compiling conditionally"
  - "TRACE directive"
  - "conditional compilation, tracing code"
ms.assetid: 56d051c3-012c-42c1-9a58-7270edc624aa
caps.latest.revision: 11
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 11
---
# How to: Compile Conditionally with Trace and Debug
Beim Debuggen einer Anwendung während der Entwicklung wird sowohl die Ablaufverfolgungsausgabe als auch die Debugausgabe im Ausgabefenster von Visual Studio angezeigt.  Allerdings müssen Sie Ihre instrumentierten Anwendungen mit aktivierter **TRACE**\-Compilerdirektive kompilieren, um Ablaufverfolgungsfeatures in eine bereitgestellte Anwendung aufzunehmen.  Dadurch kann der Ablaufverfolgungscode in die Releaseversion der Anwendung kompiliert werden.  Wenn Sie die **TRACE**\-Direktive nicht aktivieren, wird der gesamte Ablaufverfolgungscode bei der Kompilierung ignoriert und nicht in den ausführbaren Code aufgenommen, den Sie bereitstellen.  
  
 Sowohl die Ablaufverfolgungsmethoden als auch die Debugmethoden weisen zugeordnete Conditional\-Attribute auf.  Wenn das Conditional\-Attribut für die Ablaufverfolgung beispielsweise **TRUE** ist, werden alle Ablaufverfolgungsanweisungen in eine Assembly \(eine kompilierte EXE\- oder DLL\-Datei\) aufgenommen. Ist das Conditional\-Attribut **TRACE** hingegen **FALSE**, werden die Ablaufverfolgungsanweisungen nicht aufgenommen.  
  
 Für einen Build kann das Conditional\-Attribut **TRACE** oder das Conditional\-Attribut **DEBUG** aktiviert sein oder beide Conditional\-Attribute oder keines von beiden.  Daher gibt es vier Typen von Builds: **DEBUG**, **TRACE**, beide oder keines von beiden.  Manche Releasebuilds für die Produktionsbereitstellung enthalten keines von beiden, und die meisten Debugbuilds enthalten beide.  
  
 Sie können die Compilereinstellungen für die Anwendung auf verschiedene Arten angeben:  
  
-   Eigenschaftenseiten  
  
-   Befehlszeile  
  
-   **\#CONST** \(für Visual Basic\) und **\#define** \(für C\#\)  
  
### So ändern Sie die Kompilierungseinstellungen im Dialogfeld "Eigenschaftenseiten"  
  
1.  Klicken Sie im **Projektmappen\-Explorer** mit der rechten Maustaste auf den Projektknoten.  
  
2.  Wählen Sie im Kontextmenü den Befehl **Eigenschaften** aus.  
  
    -   In Visual Basic klicken Sie im linken Bereich der Eigenschaftenseite auf die Registerkarte **Kompilieren**, und klicken Sie dann auf die Schaltfläche **Erweiterte Kompilierungsoptionen**, um das Dialogfeld **Erweiterte Kompilierungsoptionen** anzuzeigen.  Aktivieren Sie die Kontrollkästchen für die Compilereinstellungen, die aktiviert werden sollen.  Deaktivieren Sie die Kontrollkästchen für die Einstellungen, die deaktiviert werden sollen.  
  
    -   Klicken Sie in C\# auf die Registerkarte **Erstellen** im linken Bereich der Eigenschaftenseite, und aktivieren Sie dann die Kontrollkästchen für die Compilereinstellungen, die aktiviert werden sollen.  Deaktivieren Sie die Kontrollkästchen für die Einstellungen, die deaktiviert werden sollen.  
  
### So kompilieren Sie instrumentierten Code über die Befehlszeile  
  
1.  Legen Sie über die Befehlszeile einen bedingten Compilerschalter fest.  Der Compiler integriert Ablaufverfolgungs\- oder Debugcode in die ausführbare Datei.  
  
     Beispielsweise wird der Ablaufverfolgungscode in eine kompilierte ausführbare Datei aufgenommen, wenn die folgende Compileranweisung über die Befehlszeile eingegeben wird:  
  
     Für Visual Basic: **vbc \/r:System.dll \/d:TRACE\=TRUE \/d:DEBUG\=FALSE MyApplication.vb**  
  
     Für C\#: **csc \/r:System.dll \/d:TRACE \/d:DEBUG\=FALSE MyApplication.cs**  
  
    > [!TIP]
    >  Lassen Sie ein Leerzeichen zwischen den Dateinamen, um mehr als eine Anwendungsdatei zu kompilieren, z. B. **MyApplication1.vb MyApplication2.vb MyApplication3.vb** oder **MyApplication1.cs MyApplication2.cs MyApplication3.cs**.  
  
     Die in den obigen Beispielen verwendeten Direktiven zur bedingten Kompilierung bedeuten Folgendes:  
  
    |Direktive|Bedeutung|  
    |---------------|---------------|  
    |`vbc`|Visual Basic\-Compiler|  
    |`csc`|C\#\-Compiler|  
    |`/r:`|Verweist auf eine externe Assembly \(EXE oder DLL\)|  
    |`/d:`|Definiert ein Symbol für bedingte Kompilierung|  
  
    > [!NOTE]
    >  Sie müssen TRACE oder DEBUG mit Großbuchstaben schreiben.  Geben Sie an der Eingabeaufforderung `vbc /?` \(für Visual Basic\) oder `csc /?` \(für C\#\) ein, um weitere Informationen zu den Befehlen zur bedingten Kompilierung anzuzeigen.  Weitere Informationen zur Befehlszeilensyntax des Visual Basic\-Compilers finden Sie unter [Erstellen von der Befehlszeile aus](../Topic/How%20to:%20Set%20Environment%20Variables%20for%20the%20Visual%20Studio%20Command%20Line.md) \(C\#\) oder [Aufrufen des Befehlszeilencompilers](../Topic/How%20to:%20Invoke%20the%20Command-Line%20Compiler%20\(Visual%20Basic\).md) \(Visual Basic\).  
  
### So führen Sie die bedingte Kompilierung mit \#CONST oder \#define durch  
  
1.  Geben Sie am Anfang der Quellcodedatei die entsprechende Anweisung für Ihre Programmiersprache ein.  
  
    |Sprache|Anweisung|Ergebnis|  
    |-------------|---------------|--------------|  
    |**Visual Basic**|**\#CONST TRACE \= true**|Aktiviert die Ablaufverfolgung|  
    ||**\#CONST TRACE \= false**|Deaktiviert die Ablaufverfolgung|  
    ||**\#CONST DEBUG \= true**|Aktiviert das Debuggen|  
    ||**\#CONST DEBUG \= false**|Deaktiviert das Debuggen|  
    |**C\#**|**\#define TRACE**|Aktiviert die Ablaufverfolgung|  
    ||**\#undef TRACE**|Deaktiviert die Ablaufverfolgung|  
    ||**\#define DEBUG**|Aktiviert das Debuggen|  
    ||**\#undef DEBUG**|Deaktiviert das Debuggen|  
  
### So deaktivieren Sie die Ablaufverfolgung oder das Debuggen  
  
1.  Löschen Sie die Compilerdirektive aus dem Quellcode.  
  
     \- oder \-  
  
2.  Kommentieren Sie die Compilerdirektive aus.  
  
    > [!NOTE]
    >  Wenn Sie kompilieren möchten, können Sie entweder **Erstellen** aus dem Menü **Erstellen** wählen oder die Befehlszeilenmethode verwenden, allerdings ohne Eingabe von **d:** zum Definieren der Symbole für bedingte Kompilierung.  
  
## Siehe auch  
 [Tracing and Instrumenting Applications](../../../docs/framework/debug-trace-profile/tracing-and-instrumenting-applications.md)   
 [How to: Create, Initialize and Configure Trace Switches](../../../docs/framework/debug-trace-profile/how-to-create-initialize-and-configure-trace-switches.md)   
 [Trace Switches](../../../docs/framework/debug-trace-profile/trace-switches.md)   
 [Trace Listeners](../../../docs/framework/debug-trace-profile/trace-listeners.md)   
 [How to: Add Trace Statements to Application Code](../../../docs/framework/debug-trace-profile/how-to-add-trace-statements-to-application-code.md)   
 [How to: Set Environment Variables for the Visual Studio Command Line](../Topic/How%20to:%20Set%20Environment%20Variables%20for%20the%20Visual%20Studio%20Command%20Line.md)   
 [How to: Invoke the Command\-Line Compiler](../Topic/How%20to:%20Invoke%20the%20Command-Line%20Compiler%20\(Visual%20Basic\).md)