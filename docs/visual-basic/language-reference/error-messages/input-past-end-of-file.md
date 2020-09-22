---
title: Eingabe nach dem Dateiende.
ms.date: 07/20/2015
f1_keywords:
- vbrID62
ms.assetid: 65292704-6e7d-4622-9f50-eb655a59b016
ms.openlocfilehash: c0cb0373fb0652e9600ac8651661708414561aca
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873971"
---
# <a name="input-past-end-of-file"></a>Eingabe nach dem Dateiende.

Eine- `Input` Anweisung liest entweder aus einer leeren oder einer Datei, in der alle Daten verwendet werden, oder verwendet die- `EOF` Funktion mit einer Datei, die für den binären Zugriff geöffnet wurde.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1. Verwenden Sie die- `EOF` Funktion unmittelbar vor der- `Input` Anweisung, um das Ende der Datei zu erkennen.  
  
2. Wenn die Datei für den binären Zugriff geöffnet ist, verwenden Sie `Seek` und `Loc` .  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:Microsoft.VisualBasic.FileSystem.Input%2A>
- <xref:Microsoft.VisualBasic.FileSystem.EOF%2A>
- <xref:Microsoft.VisualBasic.FileSystem.Seek%2A>
- <xref:Microsoft.VisualBasic.FileSystem.Loc%2A>
