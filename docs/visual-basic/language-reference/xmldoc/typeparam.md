---
title: '&lt;Typeparam&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- typeparam XML tag
- <typeparam> XML tag
ms.assetid: 1bb5ba78-f060-478c-905c-77a2e43639af
ms.openlocfilehash: 73ffb1319e6724a13a80b3cd1ca6985e4cbac05c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54567060"
---
# <a name="lttypeparamgt-visual-basic"></a>&lt;Typeparam&gt; (Visual Basic)
Definiert einen Typparametername und Beschreibung.  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<typeparam name="name">description</typeparam>  
```  
  
#### <a name="parameters"></a>Parameter  
 `name`  
 Der Name des Typparameters. Setzen Sie den Namen in einfache oder doppelte Anführungszeichen (" ").  
  
 `description`  
 Eine Beschreibung des Typparameters.  
  
## <a name="remarks"></a>Hinweise  
 Verwenden der `<typeparam>` Tag im Kommentar für einen generischen Typ oder generische Memberdeklaration, um einen der Typparameter zu beschreiben.  
  
 Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) kompiliert werden.  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel verwendet die `<typeparam>` Tag zum Beschreiben der `id` Parameter.  
  
 [!code-vb[VbVbcnXmlDocComments#8](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/typeparam_1.vb)]  
  
## <a name="see-also"></a>Siehe auch
- [XML-Kommentartags](../../../visual-basic/language-reference/xmldoc/index.md)
