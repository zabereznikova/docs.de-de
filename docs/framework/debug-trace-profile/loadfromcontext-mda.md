---
title: "loadFromContext MDA | Microsoft Docs"
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
  - "MDAs (managed debugging assistants), LoadFrom context"
  - "managed debugging assistants (MDAs), LoadFrom context"
  - "LoadFrom context"
  - "LoadFromContext MDA"
ms.assetid: a9b14db1-d3a9-4150-a767-dcf3aea0071a
caps.latest.revision: 8
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 8
---
# loadFromContext MDA
Der `loadFromContext`\-MDA \(Managed Debugging Assistant, Assistent für verwaltetes Debuggen\) wird aktiviert, wenn eine Assembly in den `LoadFrom`\-Kontext geladen wird.  Dazu kann es als Ergebnis eines Aufrufs von <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=fullName> oder anderer ähnlicher Methoden kommen.  
  
## Symptome  
 Die Verwendung einiger Ladeprogrammmethoden kann dazu führen, dass Assemblys in den `LoadFrom`\-Kontext geladen werden.  Die Verwendung dieses Kontexts kann zu unerwartetem Verhalten für die Serialisierung, Umwandlung und Auflösung von Abhängigkeiten führen.  Im Allgemeinen wird empfohlen, dass Assemblys in den `Load`\-Kontext geladen werden, um diese Probleme zu vermeiden.  Ohne diesen MDA kann nur schwer festgestellt werden, in welchen Kontext eine Assembly geladen wurde.  
  
## Ursache  
 Allgemein ausgedrückt wurde eine Assembly in den `LoadFrom`\-Kontext geladen, wenn sie aus einem Pfad außerhalb des `Load`\-Kontexts, beispielsweise aus dem globalen Assemblycache oder der <xref:System.AppDomainSetup.ApplicationBase%2A?displayProperty=fullName>\-Eigenschaft geladen wurde.  
  
## Lösung  
 Konfigurieren Sie Anwendungen so, dass <xref:System.Reflection.Assembly.LoadFrom%2A>\-Aufrufe nicht mehr benötigt werden.  Sie können hierzu die folgenden Techniken verwenden:  
  
-   Installieren Sie Assemblys im globalen Assemblycache.  
  
-   Legen Sie Assemblys im Verzeichnis <xref:System.AppDomainSetup.ApplicationBase%2A> von <xref:System.AppDomain> ab.  Im Fall der Standarddomäne befindet sich die ausführbare Datei, mit der der Prozess gestartet wurde, im Verzeichnis <xref:System.AppDomainSetup.ApplicationBase%2A>.  Möglicherweise ist es erforderlich, eine neue <xref:System.AppDomain> zu erstellen, wenn die Assembly nicht ohne weiteres verschoben werden kann.  
  
-   Fügen Sie der Konfigurationsdatei der Anwendung \(CONFIG\-Datei\) oder zusätzlichen Anwendungsdomänen einen Testpfad hinzu, wenn sich abhängige Assemblies in relativ zur Programmdatei gelegenen Unterverzeichnissen befinden.  
  
 In jedem Fall kann der Programmcode so geändert werden, dass die <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName>\-Methode verwendet wird.  
  
## Auswirkungen auf die Laufzeit  
 Der MDA hat keine Auswirkungen auf die CLR.  Es wird der Kontext gemeldet, der als Ergebnis einer Ladeanforderung verwendet wurde.  
  
## Ausgabe  
 Der MDA meldet, dass die Assembly in den `LoadFrom`\-Kontext geladen wurde.  Dabei wird der einfache Name der Assembly und der Pfad angegeben.  Es werden auch Gegenmaßnahmen vorgeschlagen, um die Verwendung des `LoadFrom`\-Kontexts zu vermeiden.  
  
## Konfiguration  
  
```  
<mdaConfig>  
  <assistants>  
    <loadFromContext />  
  </assistants>  
</mdaConfig>  
```  
  
## Beispiel  
 Im folgenden Codebeispiel wird eine Situation veranschaulicht, die zum Aktivieren dieses MDA führen kann:  
  
```  
using System.Reflection;  
namespace ConsoleApplication1  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            // The following call caused the LoadFrom context to be used  
            // because the assembly is loaded using LoadFrom and the path is   
            // located outside of the Load context probing path.   
            Assembly.LoadFrom(@"C:\Text\Test.dll");  
        }  
    }  
}  
```  
  
## Siehe auch  
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)