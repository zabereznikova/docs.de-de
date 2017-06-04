---
title: "Gewusst wie: Verweisen auf eine Assembly mit starkem Namen | Microsoft Docs"
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
  - "Assemblys [.NET Framework], Mit starken Namen"
  - "Assemblybindung, Mit starken Namen"
  - "Kompilierzeit-Assemblyverweise"
  - "Assemblys mit starken Namen, Kompilierzeitverweise"
ms.assetid: 4c6a406a-b5eb-44fa-b4ed-4e95bb95a813
caps.latest.revision: 14
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 14
---
# Gewusst wie: Verweisen auf eine Assembly mit starkem Namen
Der Vorgang des Verweisens auf Typen oder Ressourcen in einer Assembly mit starkem Namen ist in der Regel transparent.  Ein Verweis ist entweder während des Kompilierens \(frühe Bindung\) oder zur Laufzeit möglich.  
  
 Einen Verweis zur Kompilierungszeit nehmen Sie vor, indem Sie dem Compiler mitteilen, dass Ihre Assembly explizit auf eine andere Assembly verweist.  Wenn Sie einen solchen Verweis einsetzen, erhält der Compiler automatisch den öffentlichen Schlüssel der Assembly mit starkem Namen, auf die verwiesen wurde, und platziert ihn im Assemblyverweis der gerade kompilierten Assembly.  
  
> [!NOTE]
>  Eine Assembly mit starkem Namen kann nur Typen aus anderen Assemblys mit starkem Namen verwenden.  Andernfalls ist die Sicherheit der Assembly mit starkem Namen beeinträchtigt.  
  
### So verweisen Sie zur Kompilierungszeit auf eine Assembly mit starkem Namen  
  
1.  Geben Sie an der Eingabeaufforderung folgenden Befehl ein:  
  
     \<*compiler command*\> **\/reference:**\<*assembly name*\>  
  
     In diesem Befehl bezeichnet *compiler command* den Compilerbefehl für die Sprache, die Sie verwenden, und *assembly name* der Name der Assembly mit starkem Namen, auf die verwiesen wird.  Sie können auch andere Compileroptionen verwenden, z. B. die Option **\/t:library**, um eine Bibliotheksassembly zu erstellen.  
  
 Im folgenden Beispiel wird eine Assembly mit dem Namen `myAssembly.dll` erstellt, die aus einem Codemodul mit dem Namen `myAssembly.cs` auf eine Assembly mit starkem Namen, `myLibAssembly.dll`, verweist.  
  
```  
csc /t:library myAssembly.cs /reference:myLibAssembly.dll  
```  
  
### So verweisen Sie zur Laufzeit auf eine Assembly mit starkem Namen  
  
1.  Wenn Sie zur Laufzeit auf eine Assembly mit starkem Namen verweisen \(beispielsweise mit der <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName>\-Methode oder der <xref:System.Reflection.Assembly.GetType%2A?displayProperty=fullName>\-Methode\), müssen Sie den Anzeigenamen der Assembly mit starkem Namen verwenden, auf die verwiesen wird.  Anzeigenamen haben folgende Syntax:  
  
     \<*assembly name*\>**,** \<*version number*\>**,** \<*culture*\>**,** \<*public key token*\>  
  
     Beispiel:  
  
    ```  
    myDll, Version=1.1.0.0, Culture=en, PublicKeyToken=03689116d3a4ae33   
    ```  
  
     In diesem Beispiel ist `PublicKeyToken` die hexadezimale Form des öffentlichen Schlüssels.  Wenn kein Wert für die Kultur vorhanden ist, verwenden Sie `Culture=neutral`.  
  
 Der folgende Beispielcode zeigt, wie Sie diese Informationen in der <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName>\-Methode verwenden können.  
  
 [!code-cpp[Assembly.Load1#3](../../../samples/snippets/cpp/VS_Snippets_CLR/Assembly.Load1/CPP/load2.cpp#3)]
 [!code-csharp[Assembly.Load1#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Assembly.Load1/CS/load2.cs#3)]
 [!code-vb[Assembly.Load1#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Assembly.Load1/VB/load2.vb#3)]  
  
 Sie können mit dem folgenden Befehl von [Strong Name \(Sn.exe\)](../../../docs/framework/tools/sn-exe-strong-name-tool.md) den öffentlichen Schlüssel und das entsprechende Token im Hexadezimalformat drucken:  
  
 **sn \-Tp \<** *assembly* **\>**  
  
 Falls Sie über die öffentliche Schlüsseldatei verfügen, können Sie stattdessen folgenden Befehl verwenden \(beachten Sie dabei die Kleinschreibung im Unterschied zur oben genannten Option\):  
  
 **sn \-tp \<** *assembly* **\>**  
  
## Siehe auch  
 [Erstellen und Verwenden von Assemblys mit starkem Namen](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md)