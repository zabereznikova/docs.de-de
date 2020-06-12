---
title: <value> – C#-Programmierhandbuch
ms.date: 07/20/2015
f1_keywords:
- <value>
helpviewer_keywords:
- <value> C# XML tag
- value C# XML tag
ms.assetid: 08dbadaf-9ab6-43d9-9493-98e43bed199a
ms.openlocfilehash: bd6630a8d5894fda39ad289c8dd584f6d84e5490
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287193"
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
