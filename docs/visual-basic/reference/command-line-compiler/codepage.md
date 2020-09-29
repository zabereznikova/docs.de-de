---
title: -codepage
ms.date: 03/09/2018
helpviewer_keywords:
- -codepage compiler option [Visual Basic]
- codepage compiler option [Visual Basic]
- -codepage compiler option [Visual Basic]
ms.assetid: be36ec33-6800-4505-838c-4124564f5cc9
ms.openlocfilehash: 769f3586ddef7f430fa96d6101b250a5bbc4e26c
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91065735"
---
# <a name="-codepage-visual-basic"></a>-codepage (Visual Basic)

Gibt für alle Quellcodedateien in der Kompilierung die zu verwendende Codepage an.  
  
## <a name="syntax"></a>Syntax  
  
```console  
-codepage:id  
```  
  
## <a name="arguments"></a>Argumente  
  
|Begriff|Definition|  
|---|---|  
|`id`|Erforderlich. Der Compiler verwendet die von `id` angegebene Codepage, um die Codierung der Quelldateien zu interpretieren.|  
  
## <a name="remarks"></a>Hinweise  

 Sie können `-codepage` verwenden, um anzugeben, welche Codepage verwendet werden soll, um Quellcode zu kompilieren, der mit einer bestimmten Codierung gespeichert wurde. Die Option `-codepage` wirkt sich auf alle bei der Kompilierung verwendeten Quellcodedateien aus. Weitere Informationen finden Sie unter [Verwendung von Zeichencodierungsklassen in .NET](../../../standard/base-types/character-encoding.md).  
  
 Die Option `-codepage` ist nicht erforderlich, wenn die Quellcodedateien unter Verwendung der aktuellen Version der ANSI-Codepage, von Unicode oder von UTF-8 mit einer Signatur gespeichert wurden. In Visual Studio werden alle Quellcodedateien standardmäßig mit der aktuellen ANSI-Codepage gespeichert, es sei denn, der Benutzer gibt im Dialogfeld **Codierung** eine andere Codierung an. Visual Studio verwendet das Dialogfeld **Codierung**, um Quellcodedateien zu öffnen, die mit einer anderen Codepage gespeichert wurden.  
  
> [!NOTE]
> Die Option `-codepage` steht nicht in der Visual Studio-Entwicklungsumgebung zur Verfügung. Sie ist nur verfügbar, wenn Sie über die Befehlszeile kompilieren.  
  
## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](index.md)
