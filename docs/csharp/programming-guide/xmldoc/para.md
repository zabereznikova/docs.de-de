---
title: <para> – C#-Programmierhandbuch
description: 'Erfahren Sie mehr über das XML-Tag <para> ein. Mit diesem Tag können Sie dem Text in einem anderen Tag Struktur hinzufügen, beispielsweise so: <summary>, <remarks>oder <returns>.'
ms.date: 07/20/2015
f1_keywords:
- <para>
- para
helpviewer_keywords:
- <para> C# XML tag
- para C# XML tag
ms.assetid: c74b8705-29df-40b1-bff5-237492b0e978
ms.openlocfilehash: 146078bcb556b4085724ddcdac561ea868ab0481
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381852"
---
# <a name="para-c-programming-guide"></a>\<para> (C#-Programmierhandbuch)

## <a name="syntax"></a>Syntax

```xml
<para>content</para>
```

## <a name="parameters"></a>Parameter

- `content`

  Der Text des Absatzes

## <a name="remarks"></a>Hinweise

Das Tag `<para>` ist für die Verwendung innerhalb eines Tags wie [\<summary>](./summary.md), [\<remarks>](./remarks.md) oder [\<returns>](./returns.md) gedacht und ermöglicht es Ihnen, den Text zu strukturieren.

Kompilieren Sie mit [-doc](../../language-reference/compiler-options/doc-compiler-option.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.

## <a name="example"></a>Beispiel

Unter [\<summary>](./summary.md) finden Sie ein Beispiel für die Verwendung von `<para>`.

## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../index.md)
- [Empfohlene Tags für Dokumentationskommentare](./recommended-tags-for-documentation-comments.md)
