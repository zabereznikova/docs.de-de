---
title: Typweiterleitung in der Common Language Runtime
description: Durch Typweiterleitung können Sie einen Typ in eine andere .NET-Assembly verschieben, ohne Anwendungen, die die ursprüngliche Assembly verwenden, neu kompilieren zu müssen.
ms.date: 08/20/2019
helpviewer_keywords:
- assemblies [.NET], type forwarding
- type forwarding
ms.assetid: 51f8ffa3-c253-4201-a3d3-c4fad85ae097
dev_langs:
- csharp
- cpp
ms.openlocfilehash: cd166068993fb5d1a5164615de3926a06dda8098
ms.sourcegitcommit: 279fb6e8d515df51676528a7424a1df2f0917116
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92687661"
---
# <a name="type-forwarding-in-the-common-language-runtime"></a>Typweiterleitung in der Common Language Runtime

Durch Typweiterleitung können Sie einen Typ in eine andere Assembly verschieben, ohne Anwendungen, die die ursprüngliche Assembly verwenden, neu kompilieren zu müssen.  
  
 Angenommen, eine Anwendung verwendet die `Example`-Klasse in einer Assembly namens *Utility.dll*. Die Entwickler von *Utility.dll* könnten beschließen, die Assembly umzugestalten und bei diesem Vorgang die `Example`-Klasse in eine andere Assembly verschieben. Wenn die alte Version von *Utility.dll* durch die neue Version von *Utility.dll* und die zugehörige Assembly ersetzt wird, treten Fehler in der Anwendung auf, die die `Example`-Klasse verwendet, weil sie die `Example`-Klasse in der neuen Version von *Utility.dll* nicht finden kann.  
  
 Die Entwickler von *Utility.dll* können dies durch das Weiterleiten von Anforderungen an die `Example`-Klasse mit dem Attribut <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute> vermeiden. Falls das Attribut auf die neue Version von *Utility.dll* angewendet wurde, werden Anforderungen für die `Example`-Klasse an die Assembly weitergeleitet, die nun die Klasse enthält. Die vorhandene Anwendung funktioniert ohne Neukompilierung weiterhin normal.

## <a name="forward-a-type"></a>Weiterleiten eines Typs

 Die Weiterleitung eines Typs erfolgt in vier Schritten:  
  
1. Verschieben Sie den Quellcode für den Typ aus der ursprünglichen Assembly in die Zielassembly.  

2. Fügen Sie in der Assembly, in der sich der Typ ursprünglich befunden hat, ein <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute>-Objekt für den verschobenen Typ hinzu. Der folgenden Code veranschaulicht das Attribut für einen Typ namens `Example`, der verschoben wurde.  

   ```cpp  
    [assembly:TypeForwardedToAttribute(Example::typeid)]  
   ```

   ```csharp  
    [assembly:TypeForwardedToAttribute(typeof(Example))]  
   ```  

3. Kompilieren Sie die Assembly, die jetzt den Typ enthält.  

4. Führen Sie für die Assembly, in der sich der Typ befand, eine Neukompilierung mit einem Verweis auf die Assembly durch, die jetzt den Typ enthält. Wenn Sie z.B. eine C#-Datei über die Befehlszeile kompilieren, geben Sie mit [-reference (C#-Compileroptionen)](../../csharp/language-reference/compiler-options/reference-compiler-option.md) die Assembly an, die den Typ enthält. In C++ verwenden Sie die [#using](/cpp/preprocessor/hash-using-directive-cpp)-Direktive in der Quelldatei, um die Assembly anzugeben, die den Typ enthält.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute>
- [Typweiterleitung (C++/CLI)](/cpp/windows/type-forwarding-cpp-cli)
- [#using-Anweisung](/cpp/preprocessor/hash-using-directive-cpp)
