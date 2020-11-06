---
title: 'Vorgehensweise: Verweisen auf eine Assembly mit starkem Namen'
description: Dieser Artikel beschreibt, wie in einer .NET-Assembly mit starkem Namen zur Kompilierzeit oder Runtime auf Typen oder Ressourcen verwiesen wird.
ms.date: 08/20/2019
helpviewer_keywords:
- strong-named assemblies, compile-time references
- compile-time assembly referencing
- assemblies [.NET], strong-named
- assembly binding, strong-named
ms.assetid: 4c6a406a-b5eb-44fa-b4ed-4e95bb95a813
dev_langs:
- csharp
- vb
- cpp
ms.openlocfilehash: 478f786995cfc4b57f0b18b2159775db104e9cfb
ms.sourcegitcommit: 279fb6e8d515df51676528a7424a1df2f0917116
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92687693"
---
# <a name="how-to-reference-a-strong-named-assembly"></a>Vorgehensweise: Verweisen auf eine Assembly mit starkem Namen
Beim Verweisen auf Typen oder Ressourcen in einer Assembly mit starkem Namen handelt es sich in der Regel um einen transparenten Prozess. Sie können den Verweis zur Kompilierzeit (frühes Binden) oder zur Runtime vornehmen.  
  
Ein Verweis zur Kompilierzeit tritt auf, wenn Sie den Compiler darauf hinweisen, dass die Assembly, die kompiliert werden soll, explizit auf eine andere Assembly verweist. Beim Verweisen zur Kompilierzeit ruft der Compiler automatisch den öffentlichen Schlüssel der Zielassembly mit starkem Namen ab und platziert ihn in der Assemblyreferenz der Assembly, die aktuell kompiliert wird.
  
> [!NOTE]
> Eine Assembly mit starkem Namen kann nur Typen aus anderen Assemblys mit starkem Namen verwenden. Andernfalls ist die Sicherheit der Assembly mit starkem Namen beeinträchtigt.  
  
## <a name="make-a-compile-time-reference-to-a-strong-named-assembly"></a>Verweisen auf eine Assembly mit starkem Namen zur Kompilierzeit  

Geben Sie an einer Eingabeaufforderung folgenden Befehl ein:  

\<*compiler command*> **/reference:** \<*assembly name*>  

In diesem Befehl ist der *Compilerbefehl* der Befehl für die Sprache, die Sie verwenden, und *Assemblyname* ist der Name der Assembly mit starkem Namen, auf die verwiesen wird. Sie können auch andere Compileroptionen verwenden, z.B. die Option **/t:library** zum Erstellen einer Bibliothekassembly.  

Im folgenden Beispiel wird die Assembly *myAssembly.dll* erstellt, die auf die Assembly mit dem starkem Namen *myLibAssembly.dll* aus dem Codemodul *myAssembly.cs* verweist.  

```cmd
csc /t:library myAssembly.cs /reference:myLibAssembly.dll  
```  

## <a name="make-a-run-time-reference-to-a-strong-named-assembly"></a>Verweisen auf eine Assembly mit starkem Namen zur Laufzeit  
  
Wenn Sie zur Laufzeit auf eine Assembly mit starkem Namen verweisen (z. B. mit der <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>- oder <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType>-Methode), müssen Sie den Anzeigenamen der Assembly mit starkem Namen verwenden, auf die verwiesen wird. Die Syntax eines Anzeigenamens lautet wie folgt:  

\<*assembly name*>**,** \<*version number*>**,** \<*culture*>**,** \<*public key token*>  

Zum Beispiel:  

```console
myDll, Version=1.1.0.0, Culture=en, PublicKeyToken=03689116d3a4ae33
```  

In diesem Beispiel ist `PublicKeyToken` die hexadezimale Form des öffentlichen Schlüsseltokens. Wenn kein Kulturwert vorhanden ist, verwenden Sie `Culture=neutral`.  

Im folgenden Codebeispiel wird gezeigt, wie Sie diese Informationen mit der <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>-Methode verwenden.  

```cpp
Assembly^ myDll =
    Assembly::Load("myDll, Version=1.0.0.1, Culture=neutral, PublicKeyToken=9b35aa32c18d4fb1");
```

```csharp
Assembly myDll =
    Assembly.Load("myDll, Version=1.0.0.1, Culture=neutral, PublicKeyToken=9b35aa32c18d4fb1");
```

```vb
Dim myDll As Assembly = _
    Assembly.Load("myDll, Version=1.0.0.1, Culture=neutral, PublicKeyToken=9b35aa32c18d4fb1")
```

Sie können das Hexadezimalformat des öffentlichen Schlüssels und des öffentlichen Schlüsseltokens für eine bestimmte Assembly mithilfe des folgenden Befehls [Strong Name (Sn.exe)](../../framework/tools/sn-exe-strong-name-tool.md) ausgeben:  

**sn -Tp \<** *assembly* **>**  

Wenn Sie eine öffentliche Schlüsseldatei haben, können Sie stattdessen den folgenden Befehl verwenden. Beachten Sie aber den Unterschied bei der Groß- und Kleinschreibung bei der Befehlszeilenoption:  

**sn -tp \<** *public key file* **>**  

## <a name="see-also"></a>Siehe auch

- [Erstellen und Verwenden von Assemblys mit starkem Namen](create-use-strong-named.md)
