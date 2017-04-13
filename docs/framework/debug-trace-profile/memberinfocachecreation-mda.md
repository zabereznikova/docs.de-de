---
title: "memberInfoCacheCreation MDA | Microsoft Docs"
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
  - "member info cache creation"
  - "MemberInfoCacheCreation MDA"
  - "reflection, run-time errors"
  - "MDAs (managed debugging assistants), cache"
  - "cache [.NET Framework], reflection"
  - "managed debugging assistants (MDAs), cache"
  - "MemberInfo cache"
ms.assetid: 5abdad23-1335-4744-8acb-934002c0b6fe
caps.latest.revision: 8
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 8
---
# memberInfoCacheCreation MDA
Der `memberInfoCacheCreation`\-MDA \(Managed Debugging Assistant, Assistent für verwaltetes Debuggen\) wird aktiviert, wenn ein <xref:System.Reflection.MemberInfo>\-Cache erstellt wird.  Dies ist ein starkes Anzeichen für ein Programm, das ressourcenintensive Reflektionsfeatures verwendet.  
  
## Symptome  
 Das Workingset eines Programms wird vergrößert, weil das Programm ressourcenintensive Reflektionsfunktionen verwendet.  
  
## Ursache  
 Reflektionsvorgänge unter Verwendung von <xref:System.Reflection.MemberInfo>\-Objekten werden als ressourcenintensiv betrachtet, weil hierbei Metadaten gelesen werden müssen, die in Seiten außerhalb des CPU\-Cache gespeichert sind. Im Allgemeinen sind sie auch ein Anzeichen dafür, dass im Programm ein Szenario mit später Bindung verwendet wird.  
  
## Lösung  
 Sie können feststellen, an welchen Stellen im Programm Reflektion verwendet wird, indem Sie diesen MDA bereitstellen und den Code anschließend in einem Debugger ausführen oder einen Debugger an das Programm anhängen, wenn der MDA aktiviert wurde.  Im Debugger erhalten Sie eine Stapelüberwachung, in der angezeigt wird, an welcher Stelle der <xref:System.Reflection.MemberInfo>\-Cache erstellt wurde. Ausgehend von diesen Informationen können Sie ermitteln, an welcher Stelle das Programm Reflektion verwendet.  
  
 Die Lösung häng vom Zweck des Codes ab.  Dieser MDA warnt Sie, dass im Programm ein Szenario mit später Bindung eingesetzt wird.  Möglicherweise empfiehlt es sich, stattdessen ein Szenario mit früher Bindung einzusetzen oder die Leistung des Szenarios mit später Bindung zu untersuchen.  
  
## Auswirkungen auf die Laufzeit  
 Dieser MDA wird für jeden <xref:System.Reflection.MemberInfo>\-Cache aktiviert, der erstellt wird.  Die Auswirkungen auf die Leistung sind unwesentlich.  
  
## Ausgabe  
 Der MDA gibt eine Meldung aus, die angibt, dass ein <xref:System.Reflection.MemberInfo>\-Cache erstellt wurde.  Verwenden Sie einen Debugger, um eine Stapelüberwachung abzurufen, aus der ersichtlich ist, an welchen Stellen das Programm Reflektion verwendet.  
  
## Konfiguration  
  
```  
<mdaConfig>  
  <assistants>  
    <memberInfoCacheCreation/>  
  </assistants>  
</mdaConfig>  
```  
  
## Beispiel  
 In diesem Beispielcode wird der `memberInfoCacheCreation`\-MDA aktiviert.  
  
```  
using System;  
  
public class Exe  
{  
    public static void Main()  
    {  
        typeof(object).GetMethods();  
    }  
}  
```  
  
## Siehe auch  
 <xref:System.Reflection.MemberInfo>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)