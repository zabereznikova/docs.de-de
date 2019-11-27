---
title: -nologo
ms.date: 03/13/2018
helpviewer_keywords:
- -nologo compiler option [Visual Basic]
- banners [Visual Basic], suppressing startup
- nologo compiler option [Visual Basic]
- /nologo compiler option [Visual Basic]
ms.assetid: 25ef54b6-d676-4639-a2d2-a747a158bc07
ms.openlocfilehash: 03dc98c45a894304a67765c3e49cd19bbb089c8c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74335431"
---
# <a name="-nologo-visual-basic"></a>-nologo (Visual Basic)
Unterdrückt die Anzeige der Copyright Banner und Informationsmeldungen während der Kompilierung.  
  
## <a name="syntax"></a>Syntax  
  
```console  
-nologo  
```  
  
## <a name="remarks"></a>Hinweise  
 Wenn Sie `-nologo`angeben, wird vom Compiler kein Copyright Banner angezeigt. In der Standardeinstellung ist `-nologo` nicht aktiv.  
  
> [!NOTE]
> Die `-nologo`-Option ist in der Visual Studio-Entwicklungsumgebung nicht verfügbar. Sie ist nur verfügbar, wenn Sie über die Befehlszeile kompilieren.  
  
## <a name="example"></a>Beispiel  
 Mit dem folgenden Code wird `T2.vb` kompiliert und kein Copyright Banner angezeigt.  
  
```console
vbc -nologo t2.vb  
```  
  
## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
- [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
