---
title: <value> – C#-Programmierhandbuch
description: Erfahren Sie mehr über das XML-Tag <value> ein. Mit diesem Tag können Sie den Wert beschreiben, den eine Eigenschaft darstellt.
ms.date: 07/20/2015
f1_keywords:
- <value>
helpviewer_keywords:
- <value> C# XML tag
- value C# XML tag
ms.assetid: 08dbadaf-9ab6-43d9-9493-98e43bed199a
ms.openlocfilehash: d8294b477d7067653c71d1ec2047a85a0bfe6d02
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/29/2020
ms.locfileid: "87380773"
---
# <a name="value-c-programming-guide"></a>\<value> (C#-Programmierhandbuch)

## <a name="syntax"></a>Syntax

```xml
<value>property-description</value>
```

## <a name="parameters"></a>Parameter

- `property-description`

  Eine Beschreibung der Eigenschaft

## <a name="remarks"></a>Hinweise

Mit dem `<value>`-Tag können Sie den Wert beschreiben, den eine Eigenschaft darstellt. Beim Hinzufügen einer Eigenschaft über den Code-Assistenten in der Entwicklungsumgebung Visual Studio® .NET wird für die neue Eigenschaft ein [\<summary>](./summary.md)-Tag hinzugefügt. Sie sollten dann manuell ein `<value>`-Tag für die Beschreibung des Werts hinzufügen, den die Eigenschaft darstellt.

Kompilieren Sie mit [-doc](../../language-reference/compiler-options/doc-compiler-option.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.

## <a name="example"></a>Beispiel

[!code-csharp[csProgGuideDocComments#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#14)]

## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../index.md)
- [Empfohlene Tags für Dokumentationskommentare](./recommended-tags-for-documentation-comments.md)
