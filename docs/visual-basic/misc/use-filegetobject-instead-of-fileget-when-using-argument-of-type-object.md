---
title: Verwenden Sie &#39; FileGetObject &#39; anstelle von &#39; FileGet &#39; Bei Verwendung von Argument vom Typ &#39; Object &#39;
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
ms.assetid: 090b8088-895a-482a-9362-606596bac304
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2c5be466a8a0339bdb57818755d85a26d632d774
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="use-39filegetobject39-instead-of-39fileget39-when-using-argument-of-type-39object39"></a>Verwenden Sie &#39; FileGetObject &#39; anstelle von &#39; FileGet &#39; Bei Verwendung von Argument vom Typ &#39; Object &#39;
Die `FileGet` -Methode enthält ein Argument vom Typ `Object`. `FileGetObject` sollte anstelle von `FileGet` verwendet werden, um Mehrdeutigkeiten zu vermeiden.  
  
 Beachten Sie, dass die von `My.Computer.Filesystem` bereitgestellte Funktionalität benutzerfreundlicher und leistungsfähiger als `FileGet` oder `FileGetObject`ist.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Ersetzen Sie `FileGet` durch `FileGetObject`.  
  
2.  Wandeln Sie das `Object` -Argument in einen spezifischeren Typ um.  
  
## <a name="see-also"></a>Siehe auch  
   
 [My.Computer.FileSystem](xref:Microsoft.VisualBasic.FileIO.FileSystem)
