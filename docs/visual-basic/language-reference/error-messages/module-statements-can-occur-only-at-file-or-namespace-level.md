---
title: '&#39;Modul&#39; Anweisungen können nur auf Namespace- oder Dateiebene verwendet werden'
ms.date: 07/20/2015
f1_keywords:
- bc30617
- vbc30617
helpviewer_keywords:
- BC30617
ms.assetid: 5e9de8e5-d26b-4fb2-9e28-814413fe9cef
ms.openlocfilehash: 53199c2d7081445dc5490d5c54c98f93ee7522eb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33593164"
---
# <a name="39module39-statements-can-occur-only-at-file-or-namespace-level"></a>&#39;Modul&#39; Anweisungen können nur auf Namespace- oder Dateiebene verwendet werden
`Module` -Anweisungen müssen am Anfang der Quelldatei angezeigt werden unmittelbar nach `Option` und `Imports` -Anweisungen und globale Attribute Namespacedeklarationen, aber vor allen anderen Deklarationen.  
  
 **Fehler-ID:** BC30617  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Verschieben der `Module` Anweisungen am Anfang der Namespacedeklaration oder Quelldatei Datei Namespace.  
  
## <a name="see-also"></a>Siehe auch  
 [Module-Anweisung](../../../visual-basic/language-reference/statements/module-statement.md)
