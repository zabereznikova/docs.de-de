---
title: -nologo (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- -nologo compiler option [Visual Basic]
- banners [Visual Basic], suppressing startup
- nologo compiler option [Visual Basic]
- /nologo compiler option [Visual Basic]
ms.assetid: 25ef54b6-d676-4639-a2d2-a747a158bc07
ms.openlocfilehash: 07e1718554b158635b9d8b04958834e804e1fe9f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964374"
---
# <a name="-nologo-visual-basic"></a>-nologo (Visual Basic)
Unterdrückt die Anzeige der Copyright Banner und Informationsmeldungen während der Kompilierung.  
  
## <a name="syntax"></a>Syntax  
  
```  
-nologo  
```  
  
## <a name="remarks"></a>Hinweise  
 Wenn Sie angeben `-nologo`, wird vom Compiler kein Copyright Banner angezeigt. In der Standardeinstellung ist `-nologo` nicht aktiv.  
  
> [!NOTE]
> Die `-nologo` Option ist in der Visual Studio-Entwicklungsumgebung nicht verfügbar. Sie ist nur verfügbar, wenn Sie über die Befehlszeile kompilieren.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code kompiliert das `T2.vb` Copyright Banner und zeigt es nicht an.  
  
```console
vbc -nologo t2.vb  
```  
  
## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
- [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
