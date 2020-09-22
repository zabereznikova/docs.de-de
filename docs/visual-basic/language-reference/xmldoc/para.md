---
title: <para>
ms.date: 07/20/2015
helpviewer_keywords:
- <para> XML tag
- para XML tag
ms.assetid: a3a18b6c-6416-4358-94ec-37b22675fd37
ms.openlocfilehash: 0846efbaf2afacd3d0783a2d2d8e4dae3fc8b715
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90872709"
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

 Das Tag `<para>` ist für die Verwendung innerhalb eines Tags wie [\<summary>](summary.md), [\<remarks>](remarks.md) oder [\<returns>](returns.md) gedacht und ermöglicht es Ihnen, den Text zu strukturieren.  
  
 Kompilieren Sie mit [-doc](../../reference/command-line-compiler/doc.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.  
  
## <a name="example"></a>Beispiel  

 In diesem Beispiel wird das- `<para>` Tag verwendet, um den Abschnitt "Hinweise" für die `UpdateRecord` Methode in zwei Absätze aufzuteilen.  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>Weitere Informationen

- [XML-Kommentartags](index.md)
