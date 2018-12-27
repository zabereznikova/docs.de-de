---
title: Verwenden Sie 'FileGetObject' statt 'FileGet', wenn ein Argument des Typs 'Object' verwendet wird
ms.date: 07/20/2015
ms.assetid: 090b8088-895a-482a-9362-606596bac304
ms.openlocfilehash: ddbe187ed1210d238448a5ff3feaee18beea1def
ms.sourcegitcommit: 0888d7b24f475c346a3f444de8d83ec1ca7cd234
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2018
ms.locfileid: "53768010"
---
# <a name="use-filegetobject-instead-of-fileget-when-using-argument-of-type-object"></a>Verwenden Sie 'FileGetObject' statt 'FileGet', wenn ein Argument des Typs 'Object' verwendet wird
Die `FileGet`-Methode enthält ein Argument vom Typ `Object`. `FileGetObject` sollte anstelle von `FileGet` verwendet werden, um Mehrdeutigkeiten zu vermeiden.  
  
 Beachten Sie, dass die von `My.Computer.Filesystem` bereitgestellte Funktionalität benutzerfreundlicher und leistungsfähiger als `FileGet` oder `FileGetObject`ist.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Ersetzen Sie `FileGet` durch `FileGetObject`.  
  
2.  Wandeln Sie das `Object` -Argument in einen spezifischeren Typ um.  
  
## <a name="see-also"></a>Siehe auch  
   
 [My.Computer.FileSystem](xref:Microsoft.VisualBasic.FileIO.FileSystem)
