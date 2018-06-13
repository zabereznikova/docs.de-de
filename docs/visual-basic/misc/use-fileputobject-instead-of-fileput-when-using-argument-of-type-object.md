---
title: Verwendung &#39;FilePutObject&#39; anstelle von &#39;FilePut&#39; Wenn ein Argument des Typs verwendet &#39;Objekt&#39;
ms.date: 07/20/2015
f1_keywords:
- vbrUseFilePutObject
ms.assetid: d207b9b7-5898-4c13-8b03-9feefac5f726
ms.openlocfilehash: 529352d98c175981c20861205ce04c8a2ebcdca9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33641127"
---
# <a name="use-39fileputobject39-instead-of-39fileput39-when-using-argument-of-type-39object39"></a>Verwendung &#39;FilePutObject&#39; anstelle von &#39;FilePut&#39; Wenn ein Argument des Typs verwendet &#39;Objekt&#39;
Die `FilePut` -Methode enthält ein Argument des Typs `Object`. `FilePutObject` sollte anstelle von `FilePut` verwendet werden, um Mehrdeutigkeiten zu vermeiden.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Ersetzen Sie `FilePut` durch `FilePutObject`.  
  
-   Wandeln Sie das `Object` -Argument in einen spezifischeren Typ um.  
  
-   Verwenden Sie die im `My.Computer.FileSystem` -Objekt verfügbare Funktionalität.  
  
## <a name="see-also"></a>Siehe auch  
   
 [My.Computer.FileSystem](xref:Microsoft.VisualBasic.FileIO.FileSystem)  
 [My.Computer.FileSystem.WriteAllBytes](xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.WriteAllBytes%2A)
