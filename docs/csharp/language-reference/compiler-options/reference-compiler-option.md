---
title: "/reference (C# Compiler Options) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "/reference"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "/r compiler option [C#]"
  - "reference compiler option [C#]"
  - "r compiler option [C#]"
  - "/reference compiler option [C#]"
  - "-r compiler option [C#]"
  - "metadata import [C#]"
  - "public type information [C#]"
  - "-reference compiler option [C#]"
ms.assetid: 8d13e5b0-abf6-4c46-bf71-2daf2cd0a6c4
caps.latest.revision: 28
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 28
---
# /reference (C# Compiler Options)
Mit der **\/reference**\-Option importiert der Compiler [public](../../../csharp/language-reference/keywords/public.md)\-Typ\-Informationen in der angegebenen Datei in das aktuelle Projekt. Dadurch können Sie auf Metadaten aus den angegebenen Assemblydateien verweisen.  
  
## Syntax  
  
```  
/reference:[alias=]filename  
/reference:filename  
```  
  
## Argumente  
 `filename`  
 Der Name einer Datei, die ein Assemblymanifest enthält.  Um mehr als eine Datei zu importieren, schließen Sie für jede Datei eine separate **\/reference**\-Option ein.  
  
 `alias`  
 Ein gültiger C\#\-Bezeichner, der einen Stammnamespace mit allen Namespaces in der Assembly darstellt.  
  
## Hinweise  
 Um mehr als eine Datei zu importieren, schließen Sie für jede Datei eine **\/reference**\-Option ein.  
  
 Die zu importierenden Dateien müssen ein Manifest enthalten. Die Ausgabedatei muss zuvor mit einer anderen der [\/target](../../../csharp/language-reference/compiler-options/target-compiler-option.md)\-Optionen als [\/target:module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md)kompiliert werden.  
  
 **\/r** ist die Kurzform von **\/reference**.  
  
 Verwenden Sie [\/addmodule](../../../csharp/language-reference/compiler-options/addmodule-compiler-option.md), um Metadaten aus einer Ausgabedatei zu importieren, die kein Assemblymanifest enthält.  
  
 Wenn auf eine Assembly verwiesen wird \(Assembly A\), die auf eine weitere Assembly verweist \(Assembly B\), müssen Sie in folgenden Fällen auf Assembly B verweisen:  
  
-   Ein für Assembly A verwendeter Typ erbt von einem Typ oder implementiert eine Schnittstelle aus Assembly B.  
  
-   Ein Feld, eine Eigenschaft, ein Ereignis oder eine Methode mit einem Rückgabe\- oder Parametertyp aus Assembly B wird aufgerufen.  
  
 Verwenden Sie [\/lib](../../../csharp/language-reference/compiler-options/lib-compiler-option.md), um das Verzeichnis anzugeben, in dem sich ein oder mehrere Assemblyverweise befinden.  Im Thema zu **\/lib** werden auch die Verzeichnisse erläutert, in denen der Compiler nach Assemblys sucht.  
  
 Damit der Compiler einen Typ in einer Assembly \(und nicht in einem Modul\) erkennen kann, muss die Auflösung des Typs erzwungen werden. Dies kann durch die Definition einer Instanz des betreffenden Typs erfolgen.  Der Compiler verfügt über andere Möglichkeiten, um die Typnamen in einer Assembly aufzulösen. Beispielsweise wird der Typname beim Erben von einem Typ in einer Assembly vom Compiler erkannt.  
  
 Es ist in einzelnen Fällen erforderlich, aus einer Assembly heraus auf zwei unterschiedliche Versionen derselben Komponente zu verweisen.  Sie können dazu für jede Datei die Alias\-Option für den **\/reference**\-Schalter verwenden, um zwischen den beiden Dateien zu unterscheiden.  Dieser Alias wird als Qualifizierer für den Komponentennamen verwendet und in die Komponente in einer der Dateien aufgelöst.  
  
 Die CSC\-Antwortdatei \(csc.rsp\), die auf häufig verwendete .NET Framework\-Assemblys verweist, wird dabei standardmäßig verwendet.  Verwenden Sie die [\/noconfig](../../../csharp/language-reference/compiler-options/noconfig-compiler-option.md), wenn der Compiler die Datei csc.rsp nicht verwenden soll.  
  
> [!NOTE]
>  Verwenden Sie in Visual Studio das Dialogfeld **Verweis hinzufügen**.  Weitere Informationen finden Sie unter [Gewusst wie: Hinzufügen oder Entfernen von Verweisen mithilfe des Dialogfelds "Verweise hinzufügen"](http://msdn.microsoft.com/de-de/3bd75d61-f00c-47c0-86a2-dd1f20e231c9).  In Visual Studio 2010 und höheren Versionen muss zum Sicherstellen des entsprechenden Verhaltens zwischen dem Hinzufügen von Verweisen mit `/reference` und mithilfe des Dialogfelds **Verweis hinzufügen** die Eigenschaft **Interoptypen einbetten** für die hinzuzufügende Assembly auf **False** festgelegt werden.  **True** ist der Standardwert für diese Eigenschaft.  
  
## Beispiel  
 Dieses Beispiel zeigt, wie Sie die Funktion [extern\-Alias](../../../csharp/language-reference/keywords/extern-alias.md) verwenden.  
  
 Kompilieren Sie die Quelldatei, und importieren Sie Metadaten aus `grid.dll` und `grid20.dll`, ``  die bereits vorher kompiliert wurden.  Die beiden DLLs enthalten separate Versionen derselben Komponente, und Sie verwenden zwei Angaben von **\/reference** mit Alias\-Optionen, um die Quelldatei zu kompilieren.  Die Optionen sehen wie folgt aus:  
  
 \/reference:GridV1\=grid.dll und \/reference:GridV2\=grid20.dll  
  
 Dadurch werden die externen Aliase "GridV1" und "GridV2" festgelegt, die Sie in dem Programm über eine extern\-Anweisung einbinden:  
  
```  
extern alias GridV1;  
extern alias GridV2;  
// Using statements go here.  
```  
  
 Danach können Sie auf das Datenblatt\-Steuerelement aus grid.dll heraus verweisen, indem Sie dem Namen des Steuerelements "GridV1" wie folgt voranstellen:  
  
```  
GridV1::Grid  
```  
  
 Zusätzlich können Sie auf das Datenblatt\-Steuerelement aus grid20.dll heraus verweisen, wenn Sie dem Namen des Steuerelements "GridV2" wie folgt voranstellen:  
  
```  
GridV2::Grid   
```  
  
## Siehe auch  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [Gewusst wie: Ändern von Projekteigenschaften und Konfigurationseinstellungen](http://msdn.microsoft.com/de-de/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)