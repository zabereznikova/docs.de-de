---
title: /utf8output (Visual Basic) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- -utf8output compiler option [Visual Basic]
- utf8output compiler option [Visual Basic]
- /utf8output compiler option [Visual Basic]
ms.assetid: 8ab36b1e-027a-49ac-85b4-f48997d9e4d6
caps.latest.revision: 11
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 89f41527703df781f32015f386bf87c1383d9769
ms.lasthandoff: 03/13/2017

---
# <a name="utf8output-visual-basic"></a>/utf8output (Visual Basic)
Zeigt die Compilerausgabe mit UTF-8-Codierung an.  
  
## <a name="syntax"></a>Syntax  
  
```  
/utf8output[+ | -]  
```  
  
## <a name="arguments"></a>Argumente  
 `+` &#124; `-`  
 Optional. Der Standardwert für diese Option ist `/utf8output-`, d. h. Compilerausgabe nicht UTF-8-Codierung verwendet. Angeben von `/utf8output` entspricht der Angabe `/utf8output+`.  
  
## <a name="remarks"></a>Hinweise  
 Bei einigen internationalen Konfigurationen kann nicht-Compiler-Ausgabe korrekt in der Konsole angezeigt werden. Verwenden Sie in solchen Situationen `/utf8output` und -Compiler-Ausgabe in eine Datei umleiten.  
  
> [!NOTE]
>  Die `/utf8output` Option ist nicht verfügbar in der Visual Studio Development Environment; es ist nur beim Kompilieren von der Befehlszeile aus.  
  
## <a name="example"></a>Beispiel  
 Der folgende code kompiliert `In.vb` und die Compilerausgabe mit UTF-8-Codierung ausgegeben.  
  
```  
vbc /utf8output in.vb  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
