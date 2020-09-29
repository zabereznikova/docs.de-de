---
title: -optimize
ms.date: 07/20/2015
helpviewer_keywords:
- optimize compiler option [Visual Basic]
- /optimize compiler option [Visual Basic]
- optimization [Visual Basic], enabling
- -optimize compiler option [Visual Basic]
ms.assetid: fcba4a97-3622-4b87-a891-0f77deab4998
ms.openlocfilehash: d4b50d56373676bf78a7591102095209401c907d
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91097591"
---
# <a name="-optimize"></a>-optimize

Aktiviert oder deaktiviert Compileroptimierungen.  
  
## <a name="syntax"></a>Syntax  
  
```console  
-optimize[ + | - ]  
```  
  
## <a name="arguments"></a>Argumente  
  
|Begriff|Definition|  
|---|---|  
|`+` &#124; `-`|Dies ist optional. Die `-optimize-`-Option deaktiviert Compileroptimierungen. Die `-optimize+`-Option aktiviert Optimierungen. Optimierungen sind standardmäßig deaktiviert.|  
  
## <a name="remarks"></a>Hinweise  

 Durch Compileroptimierungen wird Ihre Ausgabedatei kleiner, schneller und effizienter. Da Optimierungen jedoch zu Neuanordnungen von Code in der Ausgabedatei führen, kann `-optimize+` das Debuggen erschweren.  
  
 Alle mit `-target:module` generierten Module für eine Assembly müssen dieselben `-optimize`-Einstellungen wie die Assembly verwenden. Weitere Informationen finden Sie unter [-target (Visual Basic)](target.md).  
  
 Sie können die Optionen `-optimize` und `-debug` kombinieren.  
  
|So legen Sie -optimize in der integrierten Visual Studio-Entwicklungsumgebung fest|  
|---|  
|1.  Ein Projekt auswählen in **Projektmappen-Explorer**. Klicken Sie im Menü **Projekt** auf **Eigenschaften**.<br />     <br />2.  Klicken Sie auf die Registerkarte **Kompilieren**.<br />3.  Klicken Sie auf die Schaltfläche **Erweitert** .<br />4.  Ändern Sie das Kontrollkästchen **Optimierungen aktivieren** entsprechend.|  
  
## <a name="example"></a>Beispiel  

 Der folgende Code kompiliert `T2.vb` und aktiviert Compileroptimierungen.  
  
```console
vbc t2.vb -optimize  
```  
  
## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](index.md)
- [-debug (Visual Basic)](debug.md)
- [Beispiele für Kompilierungsbefehlszeilen](sample-compilation-command-lines.md)
- [-target (Visual Basic)](target.md)
