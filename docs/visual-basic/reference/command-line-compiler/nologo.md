---
title: -Nologo (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- -nologo compiler option [Visual Basic]
- banners [Visual Basic], suppressing startup
- nologo compiler option [Visual Basic]
- /nologo compiler option [Visual Basic]
ms.assetid: 25ef54b6-d676-4639-a2d2-a747a158bc07
ms.openlocfilehash: 1b9cedc3e45795a66c203d4c86bb071045a1d3f5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54550473"
---
# <a name="-nologo-visual-basic"></a>-Nologo (Visual Basic)
Unterdrückt die Anzeige der Copyrightinformationen und informationsmeldungen während der Kompilierung.  
  
## <a name="syntax"></a>Syntax  
  
```  
-nologo  
```  
  
## <a name="remarks"></a>Hinweise  
 Bei Angabe von `-nologo`, der Compiler nicht Copyrightinformationen angezeigt. In der Standardeinstellung ist `-nologo` nicht aktiv.  
  
> [!NOTE]
>  Die `-nologo` Option ist nicht in der Visual Studio-Entwicklungsumgebung verfügbar, sondern nur, wenn Sie über die Befehlszeile kompilieren.  
  
## <a name="example"></a>Beispiel  
 Der folgende code kompiliert `T2.vb` und Copyrightinformationen nicht angezeigt.  
  
```console
vbc -nologo t2.vb  
```  
  
## <a name="see-also"></a>Siehe auch
- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
- [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
