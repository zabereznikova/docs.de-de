---
title: "Typweiterleitung in der Common&#160;Language&#160;Runtime | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Assemblys [.NET Framework], Typweiterleitung"
  - "Typweiterleitung"
ms.assetid: 51f8ffa3-c253-4201-a3d3-c4fad85ae097
caps.latest.revision: 7
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 7
---
# Typweiterleitung in der Common&#160;Language&#160;Runtime
Durch Typweiterleitung können Sie einen Typ in eine andere Assembly verschieben, ohne Anwendungen, die die ursprüngliche Assembly verwenden, neu kompilieren zu müssen.  
  
 Angenommen, eine Anwendung verwendet die `Example`\-Klasse in einer Assembly namens `Utility.dll`.  Die Entwickler von `Utility.dll` könnten beschließen, die Assembly umzugestalten und bei diesem Vorgang die `Example`\-Klasse in eine andere Assembly verschieben.  Wenn die alte Version von `Utility.dll` durch die neue Version von `Utility.dll` und die zugehörige Assembly ersetzt wird, treten Fehler in der Anwendung auf, die die `Example`\-Klasse verwendet, weil sie die `Example`\-Klasse in der neuen Version von `Utility.dll` nicht finden kann.  
  
 Die Entwickler von `Utility.dll` können dieses Problem vermeiden, indem sie Anforderungen für die `Example`\-Klasse mithilfe des <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute>\-Attributs weiterleiten.  Falls das Attribut auf die neue Version von `Utility.dll` angewendet wurde, werden Anforderungen für die `Example`\-Klasse an die Assembly weitergeleitet, die nun die Klasse enthält.  Die vorhandene Anwendung funktioniert ohne Neukompilierung weiterhin normal.  
  
> [!NOTE]
>  In .NET Framework, Version 2.0, können Sie keine Typen aus Assemblys weiterleiten, die in Visual Basic geschrieben wurden.  Eine in Visual Basic geschriebene Anwendung kann jedoch weitergeleitete Typen verarbeiten.  Wenn die Anwendung also eine in C\# oder C\+\+ codierte Assembly verwendet und ein Typ aus dieser Assembly an eine andere Assembly weitergeleitet wird, kann die Visual Basic\-Anwendung den weitergeleiteten Typ verwenden.  
  
## Weiterleiten von Typen  
 Die Weiterleitung eines Typs erfolgt in vier Schritten:  
  
1.  Verschieben Sie den Quellcode für den Typ aus der ursprünglichen Assembly in die Zielassembly.  
  
2.  Fügen Sie der Assembly, in der sich der Typ befand, ein <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute> für den verschobenen Typ hinzu.  Der  folgenden Code veranschaulicht das Attribut für einen Typ namens `Example`, der verschoben wurde.  
  
    ```csharp  
    [assembly:TypeForwardedToAttribute(typeof(Example))]  
    ```  
  
    ```cpp#  
    [assembly:TypeForwardedToAttribute(Example::typeid)]  
    ```  
  
3.  Kompilieren Sie die Assembly, die jetzt den Typ enthält.  
  
4.  Führen Sie für die Assembly, in der sich der Typ befand, eine Neukompilierung mit einem Verweis auf die Assembly durch, die jetzt den Typ enthält.  Wenn Sie z. B. eine C\#\-Datei über die Befehlszeile kompilieren, geben Sie mit der [\/reference \(Import Metadata\)](../Topic/-reference%20\(C%23%20Compiler%20Options\).md)\-Option die Assembly an, die den Typ enthält.  In C\+\+ verwenden Sie die [\#using](../Topic/%23using%20Directive%20\(C++\).md)\-Direktive in der Quelldatei, um die Assembly anzugeben, die den Typ enthält.  
  
## Siehe auch  
 <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute>   
 [Type Forwarding \(C\+\+\/CLI\)](../Topic/Type%20Forwarding%20\(C++-CLI\).md)   
 [\#using\-Direktive](../Topic/%23using%20Directive%20\(C++\).md)