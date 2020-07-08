---
title: memberInfoCacheCreation-MDA
description: Informieren Sie sich über den Mitgliedschaften für den Assistenten für verwaltetes Debuggen (MDA) in .net, der aktiviert wird, wenn ein Mitgliedschaften-Cache erstellt wird.
ms.date: 03/30/2017
helpviewer_keywords:
- member info cache creation
- MemberInfoCacheCreation MDA
- reflection, run-time errors
- MDAs (managed debugging assistants), cache
- cache [.NET Framework], reflection
- managed debugging assistants (MDAs), cache
- MemberInfo cache
ms.assetid: 5abdad23-1335-4744-8acb-934002c0b6fe
ms.openlocfilehash: c48be7ac8632b8072981be01e01997ee8c34b6b3
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "86051141"
---
# <a name="memberinfocachecreation-mda"></a>memberInfoCacheCreation-MDA
Der `memberInfoCacheCreation`-MDA (Assistent für verwaltetes Debuggen) wird aktiviert, wenn ein <xref:System.Reflection.MemberInfo>-Cache erstellt wird. Dies ist ein starkes Anzeichen für ein Programm, das ressourcenintensive Reflektionsfunktionen verwendet.  
  
## <a name="symptoms"></a>Symptome  
 Der Arbeitssatz eines Programms wird vergrößert, weil das Programm ressourcenintensive Reflektion verwendet.  
  
## <a name="cause"></a>Ursache  
 Reflektionsvorgänge, bei denen <xref:System.Reflection.MemberInfo>-Objekte einbezogen werden, gelten als ressourcenintensiv, da sie Metadaten lesen müssen, die in kalten Seiten gespeichert sind und angeben, dass das Programm irgendeine Form von spät gebundenen Szenarios verwendet.  
  
## <a name="resolution"></a>Lösung  
 Sie können feststellen, wann Reflektion in Ihrem Programm verwendet wird, indem Sie diesen MDA aktivieren und den Code dann in einem Debugger ausführen oder mit einem Debugger anfügen, wenn der MDA aktiviert wird. Mit einem Debugger erhalten Sie eine Stapelüberwachung, die zeigt, wo der <xref:System.Reflection.MemberInfo>-Cache erstellt wurde. Von dort aus können Sie feststellen, wann Ihr Programm Reflektion verwendet.  
  
 Die Lösung ist abhängig von den Zielen des Codes. Dieser MDA weist Sie darauf hin, dass das Programm ein spät gebundenes Szenario aufweist. Möglicherweise möchten Sie bestimmen, ob Sie ein früh gebundenes Szenario ersetzen oder die Leistung des spät gebundenen Szenarios berücksichtigen können.  
  
## <a name="effect-on-the-runtime"></a>Auswirkungen auf die Laufzeit  
 Dieser MDA wird für jeden <xref:System.Reflection.MemberInfo>-Cache aktiviert, das erstellt wird. Die Auswirkungen auf die Leistung sind geringfügig.  
  
## <a name="output"></a>Ausgabe  
 Der MDA gibt eine Meldung aus, die anzeigt, dass der <xref:System.Reflection.MemberInfo>-Cache erstellt wurde. Verwenden Sie einen Debugger, um eine Stapelüberwachung zu erhalten, die anzeigt, wann Ihr Programm Reflektion verwendet.  
  
## <a name="configuration"></a>Konfiguration  
  
```xml  
<mdaConfig>  
  <assistants>  
    <memberInfoCacheCreation/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a>Beispiel  
 Dieser Beispielcode aktiviert den `memberInfoCacheCreation`-MDA.  
  
```csharp
using System;  
  
public class Exe  
{  
    public static void Main()  
    {  
        typeof(object).GetMethods();  
    }  
}  
```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Reflection.MemberInfo>
- [Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen](diagnosing-errors-with-managed-debugging-assistants.md)
