---
title: -verbose
ms.date: 03/13/2018
helpviewer_keywords:
- verbose compiler option [Visual Basic]
- -verbose compiler option [Visual Basic]
- /verbose compiler option [Visual Basic]
ms.assetid: d1aec0c1-0261-421d-9adc-5b13756100be
ms.openlocfilehash: 5b3899462af7c4aa8e0f77377a8d7485975f9867
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69937261"
---
# <a name="-verbose"></a>-verbose
Bewirkt, dass der Compiler ausführliche Status-und Fehlermeldungen erzeugt.  
  
## <a name="syntax"></a>Syntax  
  
```  
-verbose[+ | -]  
```  
  
## <a name="arguments"></a>Argumente  
 `+` &#124; `-`  
 Optional. Die `-verbose` Angabe von ist identisch mit `-verbose+`der Angabe von, was bewirkt, dass der Compiler ausführliche Meldungen ausgibt. Der Standardwert für diese Option `-verbose-`ist.  
  
## <a name="remarks"></a>Hinweise  
 Die `-verbose` -Option zeigt Informationen zur Gesamtanzahl von Fehlern an, die vom Compiler ausgegeben werden, meldet, welche Assemblys von einem Modul geladen werden, und zeigt an, welche Dateien derzeit kompiliert werden.  
  
> [!NOTE]
> Die `-verbose` Option ist in der Visual Studio-Entwicklungsumgebung nicht verfügbar. Sie ist nur verfügbar, wenn Sie über die Befehlszeile kompilieren.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code kompiliert und `In.vb` weist den Compiler an, ausführliche Statusinformationen anzuzeigen.  
  
```console  
vbc -verbose in.vb  
```  
  
## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
- [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
