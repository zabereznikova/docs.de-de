---
title: Typweiterleitung in der Common Language Runtime
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- cpp
helpviewer_keywords:
- assemblies [.NET Framework], type forwarding
- type forwarding
ms.assetid: 51f8ffa3-c253-4201-a3d3-c4fad85ae097
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 18e580a67d5a983d61ab3c0b71cfc7d294468010
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="type-forwarding-in-the-common-language-runtime"></a>Typweiterleitung in der Common Language Runtime
Durch Typweiterleitung können Sie einen Typ in eine andere Assembly verschieben, ohne Anwendungen, die die ursprüngliche Assembly verwenden, neu kompilieren zu müssen.  
  
 Angenommen, eine Anwendung verwendet die `Example`-Klasse in einer Assembly namens `Utility.dll`. Die Entwickler von `Utility.dll` könnten beschließen, die Assembly umzugestalten und bei diesem Vorgang die `Example`-Klasse in eine andere Assembly verschieben. Wenn die alte Version von `Utility.dll` durch die neue Version von `Utility.dll` und die zugehörige Assembly ersetzt wird, treten Fehler in der Anwendung auf, die die `Example`-Klasse verwendet, weil sie die `Example`-Klasse in der neuen Version von `Utility.dll` nicht finden kann.  
  
 Die Entwickler von `Utility.dll` können dies durch das Weiterleiten von Anforderungen an die `Example`-Klasse mit dem Attribut <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute> vermeiden. Falls das Attribut auf die neue Version von `Utility.dll` angewendet wurde, werden Anforderungen für die `Example`-Klasse an die Assembly weitergeleitet, die nun die Klasse enthält. Die vorhandene Anwendung funktioniert ohne Neukompilierung weiterhin normal.  
  
> [!NOTE]
>  In .NET Framework, Version 2.0, können Sie keine Typen aus Assemblys weiterleiten, die in Visual Basic geschrieben wurden. Eine in Visual Basic geschriebene Anwendung kann jedoch weitergeleitete Typen verarbeiten. Wenn die Anwendung also eine in C# oder C++ codierte Assembly verwendet und ein Typ aus dieser Assembly an eine andere Assembly weitergeleitet wird, kann die Visual Basic-Anwendung den weitergeleiteten Typ verwenden.  
  
## <a name="forwarding-types"></a>Weiterleiten von Typen  
 Die Weiterleitung eines Typs erfolgt in vier Schritten:  
  
1.  Verschieben Sie den Quellcode für den Typ aus der ursprünglichen Assembly in die Zielassembly.  
  
2.  Fügen Sie in der Assembly, in der sich der Typ ursprünglich befunden hat, ein <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute>-Objekt für den verschobenen Typ hinzu. Der folgenden Code veranschaulicht das Attribut für einen Typ namens `Example`, der verschoben wurde.  
  
    ```csharp  
    [assembly:TypeForwardedToAttribute(typeof(Example))]  
    ```  
  
    ```cpp  
    [assembly:TypeForwardedToAttribute(Example::typeid)]  
    ```  
  
3.  Kompilieren Sie die Assembly, die jetzt den Typ enthält.  
  
4.  Führen Sie für die Assembly, in der sich der Typ befand, eine Neukompilierung mit einem Verweis auf die Assembly durch, die jetzt den Typ enthält. Wenn Sie z. B. eine C#-Datei über die Befehlszeile kompilieren, geben Sie mit der [/reference (C# Compiler Options)](~/docs/csharp/language-reference/compiler-options/reference-compiler-option.md)-Option die Assembly an, die den Typ enthält. In C++ verwenden Sie die [#using](http://msdn.microsoft.com/library/870b15e5-f361-40a8-ba1c-c57d75c8809a)-Direktive in der Quelldatei, um die Assembly anzugeben, die den Typ enthält.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute>  
 [Typweiterleitung (C++/CLI)](/cpp/windows/type-forwarding-cpp-cli)  
 [#using-Direktive](http://msdn.microsoft.com/library/870b15e5-f361-40a8-ba1c-c57d75c8809a)
