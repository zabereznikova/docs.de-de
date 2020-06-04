---
title: <returns>
ms.date: 07/20/2015
helpviewer_keywords:
- returns XML tag
- <returns> XML tag
ms.assetid: a03a6469-d907-425d-882f-083187950e7e
ms.openlocfilehash: edbc374332bdcd67b385ac3d061045664e942460
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84399994"
---
# <a name="returns-visual-basic"></a>\<returns> (Visual Basic)
Gibt den Rückgabewert der Eigenschaft oder Funktion an.  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<returns>description</returns>  
```  
  
## <a name="parameters"></a>Parameter  
 `description`  
 Eine Beschreibung des Rückgabewerts.  
  
## <a name="remarks"></a>Hinweise  
 Verwenden Sie das- `<returns>` Tag im Kommentar für eine Methoden Deklaration, um den Rückgabewert zu beschreiben.  
  
 Kompilieren Sie mit [-doc](../../reference/command-line-compiler/doc.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird das- `<returns>` Tag verwendet, um die Rückgabe der Funktion zu erläutern `DoesRecordExist` .  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>Weitere Informationen

- [XML-Kommentartags](index.md)
