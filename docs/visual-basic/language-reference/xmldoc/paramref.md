---
title: <paramref> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- paramref XML tag
- <paramref> XML tag
ms.assetid: 8979d53b-beb1-41b7-b41e-6bbea1c17a03
ms.openlocfilehash: 49ed974dabe747c383fa1ffa85371afecc4d2f5d
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57484276"
---
# <a name="paramref-visual-basic"></a>\<Paramref > (Visual Basic)
Formatiert ein Wort als Parameter an.  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<paramref name="name"/>  
```  
  
## <a name="parameters"></a>Parameter  
 `name`  
 Der Name des Parameters, auf den verwiesen wird. Setzen Sie den Namen in einfache oder doppelte Anführungszeichen (" ").  
  
## <a name="remarks"></a>Hinweise  
 Die `<paramref>` -Tag ermöglicht es eine Möglichkeit, um anzugeben, dass ein Wort ein Parameter ist. Die XML-Datei kann verarbeitet werden, um diesen Parameter auf unterschiedliche Weise zu formatieren.  
  
 Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) kompiliert werden.  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel verwendet die `<paramref>` -Tag zum Verweisen auf die `id` Parameter.  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>Siehe auch
- [XML-Kommentartags](../../../visual-basic/language-reference/xmldoc/index.md)
