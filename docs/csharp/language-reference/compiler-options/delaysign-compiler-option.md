---
title: "/delaysign (C# Compiler Options) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "/delaysign"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "-delaysign compiler option [C#]"
  - "delaysign compiler option [C#]"
  - "/delaysign compiler option [C#]"
ms.assetid: bcb058eb-2933-4e7f-b356-5c941db4de75
caps.latest.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 16
---
# /delaysign (C# Compiler Options)
Durch diese Option reserviert der Compiler Platz in der Ausgabedatei, damit eine digitale Signatur später hinzugefügt werden kann.  
  
## Syntax  
  
```  
/delaysign[ + | - ]  
```  
  
## Argumente  
 `+` &#124; `-`  
 Verwenden Sie **\/delaysign\-**, wenn die Assembly vollständig signiert werden soll.  Verwenden Sie **\/delaysign\+**, wenn Sie nur den öffentlichen Schlüssel in die Assembly einfügen möchten.  Der Standardwert ist **\/delaysign\-**.  
  
## Hinweise  
 Die **\/delaysign**\-Option ist nur dann wirksam, wenn sie mit [\/keyfile](../../../csharp/language-reference/compiler-options/keyfile-compiler-option.md) oder [\/keycontainer](../../../csharp/language-reference/compiler-options/keycontainer-compiler-option.md) verwendet wird.  
  
 Wenn Sie eine vollständig signierte Assembly anfordern, hasht der Compiler die Datei, die das Manifest \(die Assemblymetadaten\) enthält und signiert dieses Hash mit dem privaten Schlüssel.  Die sich ergebende digitale Signatur wird in der Datei mit dem Manifest gespeichert.  Wenn eine Assembly verzögert signiert wird, berechnet und speichert der Compiler die Signatur nicht, sondern reserviert Speicherplatz in der Datei, damit die Signatur später hinzugefügt werden kann.  
  
 Mit **\/delaysign\+** können Tester die Assembly z. B. im globalen Cache ablegen.  Nach dem Testen können Sie die Assembly dann vollständig signieren, indem Sie den privaten Schlüssel mithilfe des [Assemblylinker](../Topic/Al.exe%20\(Assembly%20Linker\).md)\-Dienstprogramms in der Assembly platzieren.  
  
 Weitere Informationen finden Sie unter [Erstellen und Verwenden von Assemblys mit starkem Namen](../Topic/Creating%20and%20Using%20Strong-Named%20Assemblies.md) und [Verzögertes Signieren einer Assembly](../Topic/Delay%20Signing%20an%20Assembly.md).  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie die Seite **Eigenschaften** für das Projekt.  
  
2.  Ändern Sie die Eigenschaft **Nur verzögerte Signierung**.  
  
 Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.ProjectProperties3.DelaySign%2A>.  
  
## Siehe auch  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [Gewusst wie: Ändern von Projekteigenschaften und Konfigurationseinstellungen](http://msdn.microsoft.com/de-de/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)