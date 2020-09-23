---
title: Verwenden Sie 'FilePutObject' statt 'FilePut', wenn ein Argument des Typs 'Object' verwendet wird.
ms.date: 07/20/2015
f1_keywords:
- vbrUseFilePutObject
ms.assetid: d207b9b7-5898-4c13-8b03-9feefac5f726
ms.openlocfilehash: c6ae755ad3eca4b1c50b83049885b6cf66f13c07
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91100333"
---
# <a name="use-fileputobject-instead-of-fileput-when-using-argument-of-type-object"></a>Verwenden Sie 'FilePutObject' statt 'FilePut', wenn ein Argument des Typs 'Object' verwendet wird.

Die `FilePut` -Methode enthält ein Argument vom Typ `Object`. `FilePutObject` sollte anstelle von `FilePut` verwendet werden, um Mehrdeutigkeiten zu vermeiden.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Ersetzen Sie `FilePut` durch `FilePutObject`.  
  
- Wandeln Sie das `Object` -Argument in einen spezifischeren Typ um.  
  
- Verwenden Sie die im `My.Computer.FileSystem` -Objekt verfügbare Funktionalität.  
  
## <a name="see-also"></a>Siehe auch

- [My. Computer. File System](xref:Microsoft.VisualBasic.FileIO.FileSystem)
- [My. Computer. File System. Write-allbytes](xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.WriteAllBytes%2A)
