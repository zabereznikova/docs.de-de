---
title: "First statement of this &#39;Sub New&#39; must be an explicit call to &#39;MyBase.New&#39; or &#39;MyClass.New&#39; because the &#39;&lt;constructorname&gt;&#39; in the base class &#39;&lt;baseclassname&gt;&#39; of &#39;&lt;derivedclassname&gt;&#39; is marked obsolete: &#39;&lt;errormessage&gt;&#39; | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc30920"
  - "bc30920"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30920"
ms.assetid: e47dc755-4294-4368-b813-2177b7677957
caps.latest.revision: 10
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 10
---
# First statement of this &#39;Sub New&#39; must be an explicit call to &#39;MyBase.New&#39; or &#39;MyClass.New&#39; because the &#39;&lt;constructorname&gt;&#39; in the base class &#39;&lt;baseclassname&gt;&#39; of &#39;&lt;derivedclassname&gt;&#39; is marked obsolete: &#39;&lt;errormessage&gt;&#39;
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Ein Klassenkonstruktor ruft einen Basisklassenkonstruktor nicht explizit auf, und der implizite Basisklassenkonstruktor ist mit dem <xref:System.ObsoleteAttribute>\-Attribut und der Direktive markiert, dies als Fehler zu behandeln.  
  
 Wenn der Konstruktor einer abgeleiteten Klasse keinen Basisklassenkonstruktor aufruft, versucht [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)], einen impliziten Aufruf eines parameterlosen Basisklassenkonstruktors zu generieren.  Wenn in der Basisklasse kein zugreifbarer Konstruktor vorhanden ist, der ohne Argumente aufgerufen werden kann, kann [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] keinen impliziten Aufruf generieren.  In diesem Fall wird der erforderliche Konstruktor mit dem <xref:System.ObsoleteAttribute>\-Attribut markiert, sodass [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] ihn nicht aufrufen kann.  
  
 Sie können ein beliebiges Programmierelement als nicht mehr in Gebrauch befindlich markieren, indem Sie <xref:System.ObsoleteAttribute> auf das Programmierelement anwenden.  In diesem Fall können Sie die <xref:System.ObsoleteAttribute.IsError%2A>\-Eigenschaft des Attributs auf `True` oder auf `False` festlegen.  Wenn Sie `True` festlegen, behandelt der Compiler einen Versuch, das Element zu verwenden, als Fehler.  Wenn Sie `False` festlegen oder als Standardwert `False` vorgeben, gibt der Compiler eine Warnung aus, sobald versucht wird, das Element zu verwenden.  
  
 **Fehler\-ID:** BC30920  
  
### So beheben Sie diesen Fehler  
  
1.  Prüfen Sie die genannte Fehlermeldung, und ergreifen Sie entsprechende Maßnahmen.  
  
2.  Fügen Sie in der abgeleiteten Klasse einen Aufruf von `MyBase.New()` oder `MyClass.New()` als erste Anweisung von `Sub New` ein.  
  
## Siehe auch  
 [Attribute](../Topic/Attributes%20\(C%23%20and%20Visual%20Basic\).md)