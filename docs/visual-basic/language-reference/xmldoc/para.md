---
title: <para>
ms.date: 07/20/2015
helpviewer_keywords:
- <para> XML tag
- para XML tag
ms.assetid: a3a18b6c-6416-4358-94ec-37b22675fd37
ms.openlocfilehash: 0e2051d1b00b881c06082b3af483890d8595899f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400072"
---
# <a name="para-visual-basic"></a>\<para> (Visual Basic)
Gibt an, dass der Inhalt als Absatz formatiert ist.  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<para>content</para>  
```  
  
## <a name="parameters"></a>Parameter  
 `content`  
 Der Text des Absatzes  
  
## <a name="remarks"></a>Hinweise  
 Das `<para>` -Tag dient zur Verwendung innerhalb eines Tags, z [\<summary>](summary.md) [\<remarks>](remarks.md) . b., oder [\<returns>](returns.md) , und ermöglicht das Hinzufügen von Struktur zum Text.  
  
 Kompilieren Sie mit [-doc](../../reference/command-line-compiler/doc.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird das- `<para>` Tag verwendet, um den Abschnitt "Hinweise" für die `UpdateRecord` Methode in zwei Absätze aufzuteilen.  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>Weitere Informationen

- [XML-Kommentartags](index.md)
