---
title: Verwenden von Grafikcontainern
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- graphics [Windows Forms], using containers
- graphics containers
- examples [Windows Forms], graphics containers
ms.assetid: 74632f91-cefa-4f51-ab7c-f9ac91942caf
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 337057e10e03712aa93b00d9c687374e53f8dd03
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="using-graphics-containers"></a>Verwenden von Grafikcontainern
Ein <xref:System.Drawing.Graphics> -Objekt stellt Methoden bereit, z. B. <xref:System.Drawing.Graphics.DrawLine%2A>, <xref:System.Drawing.Graphics.DrawImage%2A>, und <xref:System.Drawing.Graphics.DrawString%2A> zum Anzeigen von Vektorgrafiken, Rasterbilder und Text. Ein <xref:System.Drawing.Graphics> -Objekt verfügt außerdem über verschiedene Eigenschaften, die beeinflussen, die Qualität und die Ausrichtung der Elemente, die gezeichnet werden. So bestimmt beispielsweise die Glättungsmodus Mode-Eigenschaft, ob Antialiasing bei Linien und Kurven angewendet wird, und die World Transformationseigenschaft wirkt sich auf die Position und Drehung der Elemente, die gezeichnet werden.  
  
 Ein <xref:System.Drawing.Graphics> Objekt jeweiligen Ausgabegeräts zugeordnet ist. Bei Verwendung einer <xref:System.Drawing.Graphics> Objekt, das in einem Fenster Zeichnen der <xref:System.Drawing.Graphics> Objekt wird auch mit dem jeweiligen Fenster zugeordnet ist.  
  
 Ein <xref:System.Drawing.Graphics> Objekt kann betrachtet werden als Container, da es eine Reihe von Eigenschaften enthält, die Zeichnung auswirken und mit gerätespezifischen Informationen verknüpft ist. Sie können einen sekundären Container in einem vorhandenen erstellen <xref:System.Drawing.Graphics> Objekt durch Aufrufen der <xref:System.Drawing.Graphics.BeginContainer%2A> -Methode dieses <xref:System.Drawing.Graphics> Objekt.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Verwalten des Zustands eines Graphics-Objekts](../../../../docs/framework/winforms/advanced/managing-the-state-of-a-graphics-object.md)  
 Beschreibt, wie die Qualität, Clippingbereichs und Transformationen von Verwalten einer <xref:System.Drawing.Graphics> Objekt.  
  
 [Verwenden geschachtelter Grafikcontainer](../../../../docs/framework/winforms/advanced/using-nested-graphics-containers.md)  
 Zeigt, wie Container verwenden, um den Zustand steuern die <xref:System.Drawing.Graphics> Objekt.
