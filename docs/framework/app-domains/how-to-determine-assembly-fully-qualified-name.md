---
title: 'Vorgehensweise: Bestimmen des vollqualifizierten Namens einer Assembly'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- names [.NET Framework], fully qualified type names
- names [.NET Framework], assemblies
- assemblies [.NET Framework], names
ms.assetid: 009dae23-e1f6-4a64-9a9a-32e4c34802b0
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 663e7456337a2d9c413b15236e7ba1de33fbfa9b
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32743185"
---
# <a name="how-to-determine-an-assembly39s-fully-qualified-name"></a>Vorgehensweise: Bestimmen des vollqualifizierten Namens einer Assembly
Um den vollqualifizierten Namen einer Assembly im globalen Assemblycache zu ermitteln, verwenden Sie das GAC-Tool ([Gacutil.exe](../../../docs/framework/tools/gacutil-exe-gac-tool.md)). Siehe [Vorgehensweise: Anzeigen der Inhalte des globalen Assemblycaches](../../../docs/framework/app-domains/how-to-view-the-contents-of-the-gac.md).  
  
 Für Assemblys, die sich nicht im globalen Assemblycache befinden, können Sie den vollqualifizierten Assemblynamen auf verschiedene Weisen abrufen: Sie können Code verwenden, um die Informationen auf der Konsole oder in einer Variablen auszugeben. Alternativ können Sie auch den [Ildasm.exe (IL-Disassembler)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) zum Untersuchen der Metadaten verwenden, die den vollqualifizierten Namen der Assembly enthalten.  
  
-   Wenn die Assembly bereits von der Anwendung geladen wird, können Sie den Wert der <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType>-Eigenschaft abrufen, um den vollqualifizierten Namen abzurufen. Sie können diesen Ansatz verwenden, und zwar unabhängig davon, ob sich die Assembly im GAC befindet. Dies wird im Beispiel veranschaulicht.  
  
-   Wenn Sie den Dateisystempfad der Assembly kennen, können Sie die statische (`Shared` in Visual Basic) <xref:System.Reflection.AssemblyName.GetAssemblyName%2A?displayProperty=nameWithType>-Methode aufrufen, um den vollqualifizierten Assemblynamen abzurufen. Im Folgenden finden Sie ein einfaches Beispiel.  
  
     [!code-csharp[System.Reflection.AssemblyName.GetAssemblyName#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.reflection.assemblyname.getassemblyname/cs/getassemblyname1.cs#1)]
     [!code-vb[System.Reflection.AssemblyName.GetAssemblyName#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.reflection.assemblyname.getassemblyname/vb/getassemblyname1.vb#1)]  
  
-   Sie können den [Ildasm.exe (IL-Disassembler)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) verwenden, um die Metadaten der Assembly zu überprüfen, die den vollqualifizierten Namen enthalten.  
  
 Weitere Informationen zum Festlegen von Assemblyattributen wie Version, Kultur und Assemblyname finden Sie unter [Festlegen von Assemblyattributen](../../../docs/framework/app-domains/set-assembly-attributes.md). Weitere Informationen zum Vergeben eines starken Namens für eine Assembly finden Sie unter [Erstellen und Verwenden von Assemblys mit starkem Namen](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md).  
  
## <a name="example"></a>Beispiel  
 Das folgende Codebeispiel zeigt, wie Sie den voll gekennzeichneten Namen einer Assembly, die eine angegebene Klasse enthält, auf der Konsole anzeigen können. Da der Name einer Assembly abgerufen wird, die die Anwendung bereits geladen hat, spielt es keine Rolle, ob sich die Assembly im GAC befindet.  
  
 [!code-cpp[Assembly.Fullname#2](../../../samples/snippets/cpp/VS_Snippets_CLR/Assembly.FullName/CPP/example2.cpp#2)]
 [!code-csharp[Assembly.Fullname#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Assembly.FullName/CS/example2.cs#2)]
 [!code-vb[Assembly.Fullname#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Assembly.FullName/VB/example2.vb#2)]  
  
## <a name="see-also"></a>Siehe auch  
 [Assemblynamen](../../../docs/framework/app-domains/assembly-names.md)  
 [Erstellen von Assemblys](../../../docs/framework/app-domains/create-assemblies.md)  
 [Erstellen und Verwenden von Assemblys mit starkem Namen](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md)  
 [Globaler Assemblycache](../../../docs/framework/app-domains/gac.md)  
 [So sucht Common Language Runtime nach Assemblys](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 [Programmieren mit Assemblys](../../../docs/framework/app-domains/programming-with-assemblies.md)
