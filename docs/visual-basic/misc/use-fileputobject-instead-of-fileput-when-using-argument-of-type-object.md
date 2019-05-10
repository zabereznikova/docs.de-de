---
title: Verwenden Sie 'FilePutObject' statt 'FilePut', wenn ein Argument des Typs 'Object' verwendet wird.
ms.date: 07/20/2015
f1_keywords:
- vbrUseFilePutObject
ms.assetid: d207b9b7-5898-4c13-8b03-9feefac5f726
ms.openlocfilehash: bf1f50d0d8eb9b0b8518075b0e48f40645a02a25
ms.sourcegitcommit: e08b319358a8025cc6aa38737854f7bdb87183d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/29/2019
ms.locfileid: "64913216"
---
# <a name="use-fileputobject-instead-of-fileput-when-using-argument-of-type-object"></a>Verwenden Sie 'FilePutObject' statt 'FilePut', wenn ein Argument des Typs 'Object' verwendet wird.
Die `FilePut` -Methode enthält ein Argument vom Typ `Object`. `FilePutObject` sollte anstelle von `FilePut` verwendet werden, um Mehrdeutigkeiten zu vermeiden.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Ersetzen Sie `FilePut` durch `FilePutObject`.  
  
- Wandeln Sie das `Object` -Argument in einen spezifischeren Typ um.  
  
- Verwenden Sie die im `My.Computer.FileSystem` -Objekt verfügbare Funktionalität.  
  
## <a name="see-also"></a>Siehe auch

- [My.Computer.FileSystem](xref:Microsoft.VisualBasic.FileIO.FileSystem)
- [My.Computer.FileSystem.WriteAllBytes](xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.WriteAllBytes%2A)
