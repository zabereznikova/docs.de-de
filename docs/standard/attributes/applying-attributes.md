---
title: Anwenden von Attributen
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- assemblies [.NET Framework], attributes
- attributes [.NET Framework], applying
ms.assetid: dd7604eb-9fa3-4b60-b2dd-b47739fa3148
ms.openlocfilehash: 5557da1531eb55c13d1c7540a50b044d1a7b8a1d
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84276334"
---
# <a name="applying-attributes"></a>Anwenden von Attributen
Mit dem folgenden Verfahren wenden Sie ein Attribut auf ein Codeelement an.  
  
1. Definieren Sie ein neues Attribut, oder verwenden Sie ein vorhandenes Attribut, indem Sie den entsprechenden Namespace aus .NET Framework importieren.  
  
2. Wenden Sie das Attribut auf das Codeelement an, indem Sie es direkt vor dem Element platzieren.  
  
     Jede Sprache verfügt über eine eigene Attributsyntax. In C++ und C# ist das Attribut von eckigen Klammern umgeben und durch einen Leerraum, der einen Zeilenumbruch umfassen kann, vom Element getrennt. In Visual Basic ist das Attribut von spitzen Klammern umgeben, und es muss sich in derselben logischen Zeile befinden. Mithilfe des Zeilenfortsetzungszeichens kann bei Bedarf ein Zeilenumbruch eingefügt werden.
  
3. Geben Sie positionelle Parameter und benannte Parameter für das Attribut an.  
  
     Positionelle Parameter sind erforderlich und müssen vor benannten Parametern stehen. Sie entsprechen den Parametern eines der Attributkonstruktoren. Benannte Parameter sind optional und entsprechen Lese-/Schreibeigenschaften des Attributs. Geben Sie in C++ und C# für jeden optionalen Parameter `name`=`value` an, wobei `name` der Name der Eigenschaft ist. In Visual Basic geben Sie `name`:=`value` an.  
  
 Das Attribut wird beim Kompilieren von Code in Metadaten ausgegeben und ist über die Reflexionsdienste der Laufzeit für die Common Language Runtime sowie beliebige weitere benutzerdefinierte Tools und Anwendungen verfügbar.  
  
 Attributnamen enden üblicherweise auf "Attribute". Verschiedene Sprachen, die die Laufzeit unterstützen, z. B. Visual Basic und C#, erfordern jedoch nicht die vollständige Angabe eines Attributnamens. Wenn Sie z.B. <xref:System.ObsoleteAttribute?displayProperty=nameWithType> initialisieren möchten, müssen Sie lediglich mit **Veraltet** darauf verweisen.  
  
## <a name="applying-an-attribute-to-a-method"></a>Anwenden eines Attributs auf eine Methode  
 Im folgenden Codebeispiel wird die Deklaration von **System.ObsoleteAttribute** dargestellt, mit dem Code als veraltet gekennzeichnet werden kann. Die Zeichenfolge `"Will be removed in next version"` wird an das Attribut übergeben. Dieses Attribut löst eine Compilerwarnung aus. Wenn vom Attribut beschriebener Code aufgerufen wird, wird die übergebene Zeichenfolge angezeigt.  
  
 [!code-cpp[Conceptual.Attributes.Usage#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source1.cpp#3)]
 [!code-csharp[Conceptual.Attributes.Usage#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source1.cs#3)]
 [!code-vb[Conceptual.Attributes.Usage#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source1.vb#3)]  
  
## <a name="applying-attributes-at-the-assembly-level"></a>Anwenden von Attributen auf Assemblyebene  
 Wenn Sie ein Attribut auf Assemblyebene anwenden möchten, verwenden Sie das Schlüsselwort **assembly** (`Assembly` in Visual Basic). Im folgenden Codebeispiel wird **AssemblyTitleAttribute** auf Assemblyebene angewendet.  
  
 [!code-cpp[Conceptual.Attributes.Usage#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source1.cpp#2)]
 [!code-csharp[Conceptual.Attributes.Usage#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source1.cs#2)]
 [!code-vb[Conceptual.Attributes.Usage#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source1.vb#2)]  
  
 Beim Anwenden dieses Attributs wird die Zeichenfolge `"My Assembly"` im Metadatenteil der Datei im Assemblymanifest platziert. Sie können das Attribut entweder mithilfe des [MSIL-Disassemblers (Ildasm.exe)](../../framework/tools/ildasm-exe-il-disassembler.md) anzeigen lassen oder ein benutzerdefiniertes Programm erstellen, um das Attribut abzurufen.  
  
## <a name="see-also"></a>Weitere Informationen

- [Attribute](index.md)
- [Abrufen von Informationen aus Attributen](retrieving-information-stored-in-attributes.md)
- [Konzepte](/cpp/windows/attributed-programming-concepts)
- [Attribute (C#)](../../csharp/programming-guide/concepts/attributes/index.md)
- [Übersicht über Attribute (Visual Basic)](../../visual-basic/programming-guide/concepts/attributes/index.md)
