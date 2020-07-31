---
title: Ereignisse – C#-Programmierhandbuch
description: Hier erfahren Sie mehr über Ereignisse. Ereignisse aktivieren eine Klasse oder ein Objekt, um Informationen über Aktionen von Interesse an andere Klassen oder Objekte zu übermitteln.
ms.date: 07/20/2015
helpviewer_keywords:
- classes [C#], events
- C# language, events
- events [C#]
ms.assetid: a8e51b22-d294-44fb-9539-0072f06c4cb3
ms.openlocfilehash: 3160d1e381c6cb3af0f017538f9555b3fded9910
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302073"
---
# <a name="events-c-programming-guide"></a>Ereignisse (C#-Programmierhandbuch)
Ereignisse aktivieren eine [Klasse](../../language-reference/keywords/class.md) oder ein Objekt, um Informationen über Aktionen von Interesse an andere Klassen oder Objekte zu übermitteln. Die Klasse, die das Ereignis sendet (oder *auslöst*), wird als *Herausgeber* bezeichnet, und die Klassen, die das Ereignis empfangen (oder *behandeln*), werden als *Abonnenten*bezeichnet.  
  
In einer typischen C#-Windows Forms oder Web-Anwendung abonnieren Sie Ereignisse, die von Steuerelementen wie Schaltflächen und Listenfelder ausgelöst werden. Sie können die integrierte Entwicklungsumgebung (IDE) von Visual C# zum Durchsuchen der Ereignisse verwenden, die ein Steuerelement auslöst, und diejenigen wählen, die Sie behandeln möchten. Mithilfe der IDE können eine leere Ereignishandlermethode und der Code ganz einfach automatisch zu den Abonnenten des Ereignisses hinzugefügt werden. Weitere Informationen finden Sie unter [Abonnieren von Ereignissen und Kündigen von Ereignisabonnements](./how-to-subscribe-to-and-unsubscribe-from-events.md).
  
## <a name="events-overview"></a>Übersicht über Ereignisse  
 Ereignisse verfügen über folgende Eigenschaften:  
  
- Der Herausgeber wird bestimmt, wenn ein Ereignis ausgelöst wird. Die Abonnenten bestimmen, welche Aktion als Reaktion auf das Ereignis ausgeführt wird.  
  
- Ein Ereignis kann mehrere Abonnenten haben. Ein Abonnent kann mehrere Ereignisse von mehreren Herausgebern behandeln.  
  
- Ereignisse, die keine Abonnenten haben, werden nie ausgelöst.  
  
- Ereignisse werden in der Regel verwendet, um Benutzeraktionen wie Mausklicks oder Menüauswahlen in GUI-Schnittstellen zu signalisieren.  
  
- Wenn ein Ereignis mehrere Abonnenten hat, werden die Ereignishandler synchron aufgerufen, wenn ein Ereignis ausgelöst wird. Informationen zum asynchronen Aufrufen von Ereignissen finden Sie unter [Asynchrones Aufrufen von synchronen Methoden](../../../standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md).  
  
- In der .NET Framework-Klassenbibliothek basieren Ereignisse auf dem <xref:System.EventHandler>-Delegaten und der <xref:System.EventArgs>-Basisklasse.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 Weitere Informationen finden Sie unter:  
  
- [Abonnieren von Ereignissen und Kündigen von Ereignisabonnements](./how-to-subscribe-to-and-unsubscribe-from-events.md)

- [Veröffentlichen von Ereignissen, die den .NET-Richtlinien entsprechen](./how-to-publish-events-that-conform-to-net-framework-guidelines.md)

- [Auslösen von Basisklassenereignissen in abgeleiteten Klassen](./how-to-raise-base-class-events-in-derived-classes.md)

- [Implementieren von Schnittstellenereignissen](./how-to-implement-interface-events.md)

- [Implementieren benutzerdefinierter Ereignisaccessoren](./how-to-implement-custom-event-accessors.md)

## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  

Weitere Informationen erhalten Sie unter [Ereignisse](~/_csharplang/spec/classes.md#events) in der [C#-Sprachspezifikation](/dotnet/csharp/language-reference/language-specification/introduction). Die Sprachspezifikation ist die verbindliche Quelle für die Syntax und Verwendung von C#.
  
## <a name="featured-book-chapters"></a>Enthaltene Buchkapitel  
 [Delegates, Events, and Lambda Expressions](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518994%28v=orm.10%29) (Delegaten, Ereignisse und Lambda-Ausdrücke) in [C# 3.0 Cookbook, Third Edition: More than 250 solutions for C# 3.0 programmers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518995%28v=orm.10%29) (C# 3.0-Cookbook, 3. Auflage: Mehr als 250 Lösungen für C# 3.0-Programmierer)  
  
 [Delegates and Events](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652490%28v=orm.10%29) (Delegaten und Ereignisse) in [Learning C# 3.0: Master the Fundamentals of C# 3.0](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652493%28v=orm.10%29) (Erlernen von C# 3.0: Die Grundlagen von C# 3.0)  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.EventHandler>
- [C#-Programmierhandbuch](../index.md)
- [Delegaten](../delegates/index.md)
- [Erstellen von Ereignishandlern in Windows Forms](../../../framework/winforms/creating-event-handlers-in-windows-forms.md)
