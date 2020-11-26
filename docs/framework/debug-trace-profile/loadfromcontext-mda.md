---
title: loadFromContext-MDA
description: Informieren Sie sich über den LoadFromContext-MDA (Managed Debugging Assistant) in .net, der aktiviert wird, wenn eine Assembly in den LoadFrom-Kontext geladen wird.
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), LoadFrom context
- managed debugging assistants (MDAs), LoadFrom context
- LoadFrom context
- LoadFromContext MDA
ms.assetid: a9b14db1-d3a9-4150-a767-dcf3aea0071a
ms.openlocfilehash: 631939b38ace4d26d0deb5b104cc5de0df3d9f3a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96247355"
---
# <a name="loadfromcontext-mda"></a>loadFromContext-MDA

Der `loadFromContext`-MDA (Assistent für verwaltetes Debuggen) wird aktiviert, wenn eine Assembly in den `LoadFrom`-Kontext geladen wird. Diese Situation kann als Ergebnis eines <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>-Aufrufs oder anderer ähnlichen Methoden auftreten.  
  
## <a name="symptoms"></a>Symptome  

 Das Verwenden einiger Ladeprogrammmethoden kann dazu führen, dass Assemblys im `LoadFrom`-Kontext geladen werden. Das Verwenden dieses Kontexts kann zu unerwartetem Verhalten für die Serialisierung, Umwandlung und Lösung von Abhängigkeiten führen. Im Allgemeinen wird empfohlen, dass Assemblys im `Load`-Kontext geladen werden, um diese Probleme zu vermeiden. Es ist schwierig, ohne diesen MDA zu ermitteln, in welchem Kontext eine Assembly geladen wurde.  
  
## <a name="cause"></a>Ursache  

 Im Allgemeinen wurde eine Assembly in den `LoadFrom`-Kontext geladen, wenn sie aus einem Pfad außerhalb des `Load`-Kontexts geladen wurde, z.B. im globalen Assemblycache oder in der <xref:System.AppDomainSetup.ApplicationBase%2A?displayProperty=nameWithType>-Eigenschaft.  
  
## <a name="resolution"></a>Lösung  

 Konfigurieren Sie Anwendungen so, dass <xref:System.Reflection.Assembly.LoadFrom%2A>-Aufrufe nicht mehr benötigt werden. Hierfür können Sie die folgenden Verfahren verwenden:  
  
- Installieren Sie Assemblys im globalen Assemblycache.  
  
- Platzieren Sie Assemblys in das <xref:System.AppDomainSetup.ApplicationBase%2A>-Verzeichnis für die <xref:System.AppDomain>. Im Fall der Standarddomäne enthält das <xref:System.AppDomainSetup.ApplicationBase%2A>-Verzeichnis die ausführbare Datei, die den Prozess gestartet hat. Dies erfordert möglicherweise auch das Erstellen eines neuen <xref:System.AppDomain>, wenn es nicht möglich ist, die Assembly zu verschieben.  
  
- Fügen Sie einen Überprüfungspfad zu Ihrer Anwendungskonfigurationsdatei (.config) oder zu sekundären Anwendungsdomänen hinzu, wenn abhängige Assemblys in untergeordneten Verzeichnissen relativ zur ausführbaren Datei enthalten sind.  
  
 In jedem Fall kann der Code geändert werden, um die <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>-Methode zu verwenden.  
  
## <a name="effect-on-the-runtime"></a>Auswirkungen auf die Laufzeit  

 Der MDA hat keinen Einfluss auf die CLR. Er gibt den Kontext an, der als Ergebnis einer Ladeanforderung verwendet wurde.  
  
## <a name="output"></a>Ausgabe  

 Der MDA meldet, dass die Assembly in den `LoadFrom`-Kontext geladen wurde. Er gibt den einfachen Namen der Assembly und den Pfad an. Er weist auch auf Möglichkeiten hin, um das Verwenden des `LoadFrom`-Kontexts zu vermeiden.  
  
## <a name="configuration"></a>Konfiguration  
  
```xml  
<mdaConfig>  
  <assistants>  
    <loadFromContext />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a>Beispiel  

 Im folgenden Codebeispiel wird eine Situation veranschaulicht, die zum Aktivieren dieses MDA führen kann:  
  
```csharp
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
  
## <a name="see-also"></a>Weitere Informationen

- [Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen](diagnosing-errors-with-managed-debugging-assistants.md)
