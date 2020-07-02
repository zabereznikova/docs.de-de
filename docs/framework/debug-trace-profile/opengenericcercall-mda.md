---
title: OpenGenericCERCall-MDA
description: Weitere Informationen finden Sie unter opengenericcercallverwalteter debugassistent, der aktiviert werden kann, wenn der CER-Code nicht ausgeführt wird, wenn ein Thread abgebrochen oder eine Anwendungsdomäne entladen wird.
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), CER calls
- open generic CER calls
- constrained execution regions
- openGenericCERCall MDA
- CER calls
- managed debugging assistants (MDAs), CER calls
- generics [.NET Framework], open generic CER calls
ms.assetid: da3e4ff3-2e67-4668-9720-fa776c97407e
ms.openlocfilehash: 4df33b0cdf9759edec47f02b3feb671d03284ec8
ms.sourcegitcommit: c23d9666ec75b91741da43ee3d91c317d68c7327
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85803936"
---
# <a name="opengenericcercall-mda"></a>OpenGenericCERCall-MDA

Der `openGenericCERCall`-MDA (Assistent für verwaltetes Debuggen) wird aktiviert, um zu warnen, dass ein CER-Diagramm mit generischen Typvariablen in der Stammmethode zum Zeitpunkt der JIT-Kompilierung oder der nativen Imagegenerierung verarbeitet wird und mindestens eine der generischen Typvariablen ein Objektverweistyp ist.

## <a name="symptoms"></a>Symptome

CER-Code, der nicht ausgeführt wird, wenn ein Thread abgebrochen oder eine Anwendungsdomäne entladen wird.

## <a name="cause"></a>Ursache

Zum Zeitpunkt der JIT-Kompilierung ist eine Instanziierung, die einen Objektverweistyp enthält, nur repräsentativ, da der resultierende Code freigegeben wird und jede Variable des Objektverweistyps ggf. ein beliebiger Objektverweistyp sein kann. Dies kann die Vorbereitung einiger Laufzeitressourcen im Voraus verhindern.

Methoden mit generischen Typvariablen können Ressourcen im Hintergrund verzögert zuordnen. Diese werden als generische Wörterbucheinträge bezeichnet. Beispielsweise muss für die Anweisung, `List<T> list = new List<T>();` bei der `T` es sich um eine generische Typvariable handelt, die Laufzeit nachschlagen und möglicherweise die genaue Instanziierung zur Laufzeit erstellen, z `List<Object>, List<String>` . b., usw. Dies kann aus einer Vielzahl von Gründen fehlschlagen, die außerhalb der Kontrolle des Entwicklers liegen, z.B. fehlendem Arbeitsspeicher.

Dieser MDA sollte nur zum Zeitpunkt der JIT-Kompilierung aktiviert werden, und nicht bei einer genauen Instanziierung.

Wenn dieser MDA aktiviert wird, ist es wahrscheinlich, dass die CERs für fehlerhafte Instanziierungen nicht funktionsfähig sind. Die Common Language Runtime hat in der Tat nicht versucht, einen CER unter den Umständen zu implementieren, die zur Aktivierung der MDA geführt haben. Wenn der Entwickler eine freigegebene Instanziierung des CER verwendet, dann werden JIT-Kompilierungsfehler, Fehler beim Laden von Generics oder Threadabbrüche innerhalb des Bereichs des vorgesehenen CERs nicht abgefangen.

## <a name="resolution"></a>Lösung

Verwenden Sie keine generischen Typvariablen, die Objektverweistypen für Methoden sind, die möglicherweise eine CER enthalten.

## <a name="effect-on-the-runtime"></a>Auswirkungen auf die Laufzeit

Dieser MDA hat keine Auswirkungen auf die CLR.

## <a name="output"></a>Output

Im folgenden finden Sie ein Beispiel für die Ausgabe dieses MDA:
  
 ```output
 Method 'GenericMethodWithCer', which contains at least one constrained execution region, cannot be prepared automatically since it has one or more unbound generic type parameters.
 The caller must ensure this method is prepared explicitly at run time prior to execution.
 method name="GenericMethodWithCer"
 declaringType name="OpenGenericCERCall"
 ```

## <a name="configuration"></a>Konfiguration

```xml
<mdaConfig>
  <assistants>
    <openGenericCERCall/>
  </assistants>
</mdaConfig>
```  

## <a name="example"></a>Beispiel

Der CER-Code wird nicht ausgeführt.

```csharp
using System;
using System.Collections.Generic;
using System.Runtime.CompilerServices;

class Program
{
    static void Main(string[] args)
    {
        CallGenericMethods();
    }
    static void CallGenericMethods()
    {
        // This call is correct. The instantiation of the method
        // contains only nonreference types.
        MyClass.GenericMethodWithCer<int>();

        // This call is incorrect. A shared version of the method that
        // cannot be completely analyzed will be JIT-compiled. The
        // MDA will be activated at JIT-compile time, not at run time.
        MyClass.GenericMethodWithCer<String>();
    }
}

class MyClass
{
    public static void GenericMethodWithCer<T>()
    {
        RuntimeHelpers.PrepareConstrainedRegions();
        try
        {

        }
        finally
        {
            // This is the start of the CER.
            Console.WriteLine("In finally block.");
        }
    }
}
```

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareMethod%2A>
- <xref:System.Runtime.ConstrainedExecution>
- [Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen](diagnosing-errors-with-managed-debugging-assistants.md)
