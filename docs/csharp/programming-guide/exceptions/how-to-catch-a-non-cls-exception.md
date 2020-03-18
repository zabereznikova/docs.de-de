---
title: Abfangen einer Nicht-CLS-Ausnahme
ms.date: 07/20/2015
helpviewer_keywords:
- exceptions [C#], non-CLS
ms.assetid: db4630b3-5240-471a-b3a7-c7ff6ab31e8d
ms.openlocfilehash: 635cf0a9142f56dea4b2722fbf3f3eda505d85ee
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "75346277"
---
# <a name="how-to-catch-a-non-cls-exception"></a>Abfangen einer Nicht-CLS-Ausnahme
Einige .NET-Sprachen, einschließlich C++/CLI, erlauben Objekten, Ausnahmen auszulösen, die nicht aus <xref:System.Exception> stammen. Diese Ausnahmen werden als *Nicht-CLS-Ausnahmen* oder *Nicht-Ausnahmen* bezeichnet. In C# können Sie keine Nicht-CLS-Ausnahmen auslösen. Sie können sie jedoch auf zwei Arten abfangen:  
  
- Innerhalb eines `catch (RuntimeWrappedException e)`-Blocks
  
     In der Standardeinstellung fängt eine Visual C#-Assembly Nicht-CLS-Ausnahmen als umschlossene Ausnahmen ab. Verwenden Sie diese Methode, wenn Sie Zugriff auf die ursprüngliche Ausnahme benötigen, auf die über die Eigenschaft <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A?displayProperty=nameWithType> zugegriffen werden kann. Weiter unten in diesem Thema wird erläutert, wie Abfragen auf diese Art und Weise abgefangen werden können.  
  
- Innerhalb eines allgemeinen Catch-Blocks (ein Catch-Block ohne angegebenen Ausnahmetyp), der nach allen anderen `catch`-Blocks eingefügt wird
  
     Verwenden Sie diese Methode, wenn Sie eine Aktion (z.B. das Schreiben in eine Protokolldatei) als Reaktion auf Nicht-CLS-Ausnahmen ausführen möchten und Sie keinen Zugriff auf die Ausnahmeinformationen benötigen. Standardmäßig umschließt die Common Language Runtime alle Ausnahmen. Um dieses Verhalten zu deaktivieren, fügen Sie dieses Attribut auf Assemblyebene Ihrem Code hinzu, in der Regel in die Datei „AssemblyInfo.cs“: `[assembly: RuntimeCompatibilityAttribute(WrapNonExceptionThrows = false)]`.  
  
### <a name="to-catch-a-non-cls-exception"></a>So fangen Sie eine Nicht-CLS-Ausnahme ab  
  
Greifen Sie in einem `catch(RuntimeWrappedException e)`-Block über die Eigenschaft <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A?displayProperty=nameWithType> auf die ursprüngliche Ausnahme zu.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie Sie eine Nicht-CLS-Ausnahme abfangen, die von einer in C++/CLI geschriebenen Klassenbibliothek ausgelöst wurde. Beachten Sie, dass in diesem Beispiel der C#-Clientcode im Voraus weiß, dass der Ausnahmetyp, der ausgelöst wird, <xref:System.String?displayProperty=nameWithType> lautet. Wandeln Sie die Eigenschaft <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A?displayProperty=nameWithType> in den ursprünglichen Typ um, solange dieser Typ über Ihren Code erreicht werden kann.  
  
```csharp
// Class library written in C++/CLI.
var myClass = new ThrowNonCLS.Class1();

try
{
    // throws gcnew System::String(  
    // "I do not derive from System.Exception!");  
    myClass.TestThrow();
}
catch (RuntimeWrappedException e)
{
    String s = e.WrappedException as String;
    if (s != null)
    {
        Console.WriteLine(s);
    }
}
```  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Runtime.CompilerServices.RuntimeWrappedException>
- [Ausnahmen und Ausnahmebehandlung](./index.md)
