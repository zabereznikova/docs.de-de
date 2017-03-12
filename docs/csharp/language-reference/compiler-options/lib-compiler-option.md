---
title: "/lib (C# Compiler Options) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "/lib"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "lib compiler option [C#]"
  - "-lib compiler option [C#]"
  - "/lib compiler option [C#]"
ms.assetid: b0efcc88-e8aa-4df4-a00b-8bdef70b7673
caps.latest.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 16
---
# /lib (C# Compiler Options)
Die Option **\/lib** gibt die Position von Assemblys an, auf die mit der Option [\/reference \(Import Metadata\)](../../../csharp/language-reference/compiler-options/reference-compiler-option.md) verwiesen wird.  
  
## Syntax  
  
```  
/lib:dir1[,dir2]  
```  
  
## Argumente  
 `dir1`  
 ein Verzeichnis, in dem der Compiler sucht, wenn eine Assembly, auf die verwiesen wird, nicht im aktuellen Arbeitsverzeichnis \(dem Verzeichnis, von dem aus Sie den Compiler starten\) oder im Systemverzeichnis der Common Language Runtime gefunden wird.  
  
 `dir2`  
 ein oder mehrere Verzeichnisse, die nach Verweisen auf Assemblys durchsucht werden.  Trennen Sie zusätzliche Verzeichnisnamen mit einem Komma ohne vor\- bzw. nachstehendes Leerzeichen zwischen den Namen.  
  
## Hinweise  
 Der Compiler sucht in der folgenden Reihenfolge nach Assemblyverweisen, die nicht voll qualifiziert sind:  
  
1.  Aktuelles Arbeitsverzeichnis.  Dies ist das Verzeichnis, von dem aus der Compiler aufgerufen wurde.  
  
2.  Systemverzeichnis der Common Language Runtime.  
  
3.  Mit **\/lib** angegebene Verzeichnisse.  
  
4.  Verzeichnisse, die durch die **LIB**\-Umgebungsvariable angegeben werden.  
  
 Verwenden Sie **\/reference**, um einen Assemblyverweis anzugeben.  
  
 Die **\/lib**\-Option ist additiv. Wenn Sie sie mehrmals angeben, werden die entsprechenden Werte an die vorherigen Werte angehängt.  
  
 Anstatt **\/lib** zu verwenden, können Sie auch die erforderlichen Assemblys in das Arbeitsverzeichnis kopieren. Auf diese Weise können Sie den Assemblynamen einfach an **\/reference** übergeben.  Danach können Sie die Assemblys aus dem Arbeitsverzeichnis löschen.  Da der Pfad der abhängigen Assembly nicht im Assemblymanifest angegeben wurde, kann die Anwendung auf dem Zielcomputer gestartet werden. Sie sucht und verwendet dann die Assembly im globalen Assemblycache.  
  
 Obwohl der Compiler auf die Assembly verweisen kann, hat dies nicht automatisch zur Folge, dass sie zur Laufzeit von der Common Language Runtime gefunden und geladen wird.  Weitere Informationen zur Laufzeitsuche nach Verweisassemblys finden Sie unter [So sucht Common Language Runtime nach Assemblys](../Topic/How%20the%20Runtime%20Locates%20Assemblies.md).  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  
  
2.  Klicken Sie auf die Eigenschaftenseite **Verweispfad**.  
  
3.  Ändern Sie den Inhalt des Listenfelds.  
  
 Informationen über das programmgesteuerte Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.ProjectProperties3.ReferencePath%2A>.  
  
## Beispiel  
 In diesem Beispiel wird **t2.cs** kompiliert, um eine EXE\-Datei zu erstellen.  Der Compiler sucht im Arbeitsverzeichnis und im Stammverzeichnis von Laufwerk C nach Assemblyverweisen.  
  
```  
csc /lib:c:\ /reference:t2.dll t2.cs  
```  
  
## Siehe auch  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [Gewusst wie: Ändern von Projekteigenschaften und Konfigurationseinstellungen](http://msdn.microsoft.com/de-de/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)