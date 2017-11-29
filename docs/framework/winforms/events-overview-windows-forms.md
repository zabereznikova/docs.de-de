---
title: "Übersicht über Ereignisse (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms, event handling
- events [Windows Forms], about events
- delegates [Windows Forms], multicast
- delegates [Windows Forms], events and
- multicast event delegates
- Windows Forms controls, events
ms.assetid: 814a6a43-a312-4791-88d8-f75f9a4f8c4c
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4989a13ef16445bc19b3dc3c6d265d943a464c62
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="events-overview-windows-forms"></a>Übersicht über Ereignisse (Windows Forms)
Ein Ereignis ist eine Aktion, auf die Sie antworten oder im Code „behandeln“ können. Ereignisse können durch eine Benutzeraktion generiert werden, z. B. durch Klicken mit der Maus oder Drücken auf eine Taste; durch Programmcode; oder durch das System.  
  
 Ereignisgesteuerte Anwendungen führen Code als Reaktion auf ein Ereignis aus. Jedes Formular und jedes Steuerelement macht eine vordefinierte Gruppe von Ereignissen verfügbar, die Sie programmieren können. Wenn eines dieser Ereignisse auftritt und Code im zugeordneten Ereignishandler vorhanden ist, wird der Code aufgerufen.  
  
 Die von einem Objektarray ausgelösten Ereignistypen unterscheiden sich, viele ähneln aber den meisten Steuerelementen. Die meisten Objekte behandeln beispielsweise ein <xref:System.Windows.Forms.Control.Click>-Ereignis. Wenn ein Benutzer auf ein Formular klickt, wird der Code im <xref:System.Windows.Forms.Control.Click>-Ereignishandler des Formulars ausgeführt.  
  
> [!NOTE]
>  Viele Ereignisse treten im Zusammenhang mit anderen Ereignissen auf. Wenn beispielsweise ein <xref:System.Windows.Forms.Control.DoubleClick>-Ereignis auftritt, treten auch die <xref:System.Windows.Forms.Control.MouseDown>, <xref:System.Windows.Forms.Control.MouseUp>- und <xref:System.Windows.Forms.Control.Click>-Ereignisse auf.  
  
 Informationen zum Auslösen und Nutzen eines Ereignisses finden Sie unter [Ereignisse](../../../docs/standard/events/index.md).  
  
## <a name="delegates-and-their-role"></a>Delegaten und ihre Rolle  
 Delegaten sind Klassen, die häufig in den in [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] zu erstellenden ereignishandhabenden Mechanismen verwendet werden. Delegaten entsprechen in etwa Funktionszeigern, die häufig in [!INCLUDE[vcprvc](../../../includes/vcprvc-md.md)] und anderen objektorientierten Sprachen verwendet werden. Im Gegensatz zu Funktionszeigern sind Delegaten objektorientiert, typsicher und sicher. Darüber hinaus bestehen Sie im Vergleich zu Funktionszeigern, die nur einen Verweis zu einer bestimmten Funktion enthalten, aus einem Verweis zu einem Objekt und Verweisen zu einem oder mehren Methoden in dem Objekt.  
  
 Das Ereignismodell verwendet *Delegaten* zum Binden von Ereignissen an die Methoden, die verwendet werden, zu deren Behandlung. Mit dem Delegat können andere Klassen für eine Ereignisbenachrichtigung registriert werden, indem eine Handlermethode angegeben wird. Wenn das Ereignis auftritt, ruft der Delegat die gebundene Methode auf. Weitere Informationen zum Definieren von Delegaten finden Sie unter [Ereignisse](../../../docs/standard/events/index.md).  
  
 Delegaten können an eine einzelne oder mehrere Methoden gebunden werden, das bezeichnet man als Multicasting. Beim Erstellen eines Delegaten für ein Ereignis erstellen Sie (oder der Windows-Forms-Designer) in der Regel ein Multicast-Ereignis. Eine seltene Ausnahme dazu ist möglicherweise ein Ereignis, das zu einer bestimmten Prozedur führt (z. B. das Anzeigen eines Dialogfelds), die logischerweise nicht mehrmals pro Ereignis auftritt. Informationen über das Erstellen von Multicastdelegaten finden Sie unter [wie: Kombinieren von Delegaten (Multicastdelegaten)](~/docs/csharp/programming-guide/delegates/how-to-combine-delegates-multicast-delegates.md).  
  
 Ein Multicast-Delegat verwaltet eine Aufrufliste der Methoden, an die er gebunden ist. Der Multicast-Delegat unterstützt eine <xref:System.Delegate.Combine%2A>-Methode zum Hinzufügen einer Methode zur Aufrufliste und eine <xref:System.Delegate.Remove%2A>-Methode, um sie zu entfernen.  
  
 Wenn ein Ereignis von der Anwendung aufgezeichnet wird, löst das Steuerelement das Ereignis aus, indem es den Delegaten für das Ereignis aufruft. Der Delegat wiederum ruft die gebundene Methode auf. Im häufigsten Fall (einem Multicast-Delegat) ruft der Delegat wiederum jede gebundene Methode in der Aufrufliste auf, sodass eine eins-zu-viele-Benachrichtigung bereitgestellt wird. Das heißt, das Steuerelement muss keine Zielobjektliste für die Ereignisbenachrichtigung verwalten – der Delegat behandelt alle Registrierungen und Benachrichtigungen.  
  
 Mit Delegaten können auch mehrere Ereignisse an dieselbe Methode gebunden werden, sodass eine viele-zu-eins-Benachrichtigung bereitgestellt werden kann.  Ein Klick-Ereignis einer Schaltfläche und ein Menübefehl-Klick-Ereignis können beide denselben Delegaten aufrufen, der dann eine einzelne Methode aufruft, um diese separaten Ereignisse gleich zu behandeln.  
  
 Der mit Delegaten verwendete Bindungsmechanismus ist dynamisch: ein Delegat kann zur Laufzeit an jede Methode gebunden werden, dessen Signatur mit der des Ereignishandlers übereinstimmt. Mit dieser Funktion können Sie die gebundene Methode abhängig von einer Bedingung einrichten oder ändern und einen Ereignishandler dynamisch an ein Steuerelement anfügen.  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen von Ereignishandlern in Windows Forms](../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md)  
 [Übersicht über Ereignishandler](../../../docs/framework/winforms/event-handlers-overview-windows-forms.md)
