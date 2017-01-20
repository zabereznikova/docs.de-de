---
title: "&#39;Get&#39; accessor of property &#39;&lt;propertyname&gt;&#39; is not accessible | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc31103"
  - "bc31103"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC31103"
ms.assetid: 3c346c32-7669-4b04-841d-7a9df9cb703e
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;Get&#39; accessor of property &#39;&lt;propertyname&gt;&#39; is not accessible
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Eine Anweisung versucht, den Wert einer Eigenschaft abzurufen, obwohl sie über keinen Zugriff auf die `Get`\-Prozedur der Eigenschaft verfügt.  
  
 Wenn die [Get Statement](../../../visual-basic/language-reference/statements/get-statement.md) mit einer restriktiveren Zugriffsebene als die zugehörige [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md) markiert ist, kann das Lesen des Eigenschaftswerts in den folgenden Fällen fehlschlagen:  
  
-   Die `Get`\-Anweisung ist als [Private](../../../visual-basic/language-reference/modifiers/private.md) markiert, und der aufrufende Code befindet sich außerhalb der Klasse oder Struktur, in der die Eigenschaft definiert ist.  
  
-   Die `Get`\-Anweisung ist als [Protected](../../../visual-basic/language-reference/modifiers/protected.md) markiert, und der aufrufende Code befindet sich weder in der Klasse oder Struktur, in der die Eigenschaft definiert ist, noch in einer abgeleiteten Klasse.  
  
-   Die `Get`\-Anweisung ist als [Friend](../../../visual-basic/language-reference/modifiers/friend.md) markiert, und der aufrufende Code befindet sich nicht in derselben Assembly, in der die Eigenschaft definiert ist.  
  
 **Fehler\-ID:** BC31103  
  
### So beheben Sie diesen Fehler  
  
-   Wenn Sie über die Quellcodeverwaltung des die Eigenschaft definierenden Codes verfügen, empfiehlt es sich, die `Get`\-Prozedur mit derselben Zugriffsebene wie die Eigenschaft selbst zu deklarieren.  
  
-   Wenn Sie nicht über die Quellcodeverwaltung des die Eigenschaft definierenden Codes verfügen oder wenn Sie die Zugriffsebene der `Get`\-Prozedur stärker einschränken müssen als die Eigenschaft selbst, verschieben Sie die Anweisung zum Lesen des Eigenschaftswerts in einen Bereich des Codes, der besser auf die Eigenschaft zugreifen kann.  
  
## Siehe auch  
 [Eigenschaftenprozeduren](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)   
 [How to: Declare a Property with Mixed Access Levels](../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-a-property-with-mixed-access-levels.md)