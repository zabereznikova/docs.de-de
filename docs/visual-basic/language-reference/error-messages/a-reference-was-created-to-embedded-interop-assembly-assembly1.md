---
title: Ein Verweis erstellt wurde, die eingebettete Interopassembly &#39; &lt;assembly1&gt;&#39; aufgrund eines indirekten Verweises auf diese Assembly aus Assembly &#39;&lt; Assembly2&gt;&#39;
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc40059
- bc40059
helpviewer_keywords:
- VBC40059
- BC40059
ms.assetid: 520e39cb-8ab6-46f5-aa00-08afd51b4b7c
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: aaaa7460ade00ad4232807ce11ee125e270742bf
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="a-reference-was-created-to-embedded-interop-assembly-39ltassembly1gt39-because-of-an-indirect-reference-to-that-assembly-from-assembly-39ltassembly2gt39"></a>Ein Verweis erstellt wurde, die eingebettete Interopassembly &#39; &lt;assembly1&gt;&#39; aufgrund eines indirekten Verweises auf diese Assembly aus Assembly &#39;&lt; Assembly2&gt;&#39;
Es wurde ein Verweis auf die eingebettete Interopassembly „\<assembly1>“ aufgrund eines indirekten Verweises auf diese Assembly aus Assembly „\<assembly2>“ erstellt. Ändern Sie ggf. für beide Assembly die Eigenschaft 'Interoptypen einbetten'.  
  
 Sie haben einen Verweis auf eine Assembly (assembly1) hinzugefügt, deren `Embed Interop Types`-Eigenschaft auf `True` festgelegt ist. Dadurch wird der Compiler angewiesen, Interoptypinformationen von dieser Assembly einzubetten. Der Compiler kann jedoch keine Interoptypinformationen von dieser Assembly einbetten, da eine andere Assembly, auf die verwiesen wird (assembly2), ebenfalls auf diese Assembly verweist (assembly1) und die `Embed Interop Types`-Eigenschaft auf `False` festgelegt ist.  
  
> [!NOTE]
>  Das Festlegen der `Embed Interop Types`-Eigenschaft in einem Assemblyverweis auf `True` entspricht dem Verweisen auf die Assembly mit der `/link`-Option für den Befehlszeilencompiler.  
  
 **Fehler-ID:** BC40059  
  
### <a name="to-address-this-warning"></a>So reagieren Sie auf diese Warnung  
  
-   Um Interoptypinformationen für beide Assemblys einzubetten, legen Sie die `Embed Interop Types`-Eigenschaft in allen Verweisen auf assembly1 auf `True` fest.  
  
-   Um die Warnung zu entfernen, können Sie die `Embed Interop Types`-Eigenschaft von assembly1 auf `False` festlegen. In diesem Fall werden Interoptypinformationen von eine primäre Interopassembly (PIA) bereitgestellt.  
  
## <a name="see-also"></a>Siehe auch  
 [/link (Visual Basic)](../../../visual-basic/reference/command-line-compiler/link.md)  
 [Interoperabilität mit nicht verwaltetem Code](../../../framework/interop/index.md)
