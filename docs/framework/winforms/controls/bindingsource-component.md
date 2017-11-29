---
title: BindingSource-Komponente
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data binding [Windows Forms], Windows Forms
- Windows Forms, data binding control
- BindingSource component [Windows Forms]
ms.assetid: 3e2faf4c-f5b8-4fa6-9fbc-f59c37ec2fb9
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 006cafafdf8e3c3f4da77394d6155fa52e113b58
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="bindingsource-component"></a><span data-ttu-id="85721-102">BindingSource-Komponente</span><span class="sxs-lookup"><span data-stu-id="85721-102">BindingSource Component</span></span>
<span data-ttu-id="85721-103">Kapselt eine Datenquelle zum Binden an Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="85721-103">Encapsulates a data source for binding to controls.</span></span>  
  
 <span data-ttu-id="85721-104">Die <xref:System.Windows.Forms.BindingSource>-Komponente dient zwei Zwecken.</span><span class="sxs-lookup"><span data-stu-id="85721-104">The <xref:System.Windows.Forms.BindingSource> component serves two purposes.</span></span> <span data-ttu-id="85721-105">Erstens stellt sie eine Dereferenzierungsschicht bereit, wenn die Steuerelemente in einem Formular an Daten gebunden werden.</span><span class="sxs-lookup"><span data-stu-id="85721-105">First, it provides a layer of indirection when binding the controls on a form to data.</span></span> <span data-ttu-id="85721-106">Bei diesem Vorgang wird die <xref:System.Windows.Forms.BindingSource>-Komponente an die Datenquelle gebunden, und anschließend werden die Steuerelemente im Formular an die <xref:System.Windows.Forms.BindingSource>-Komponente gebunden.</span><span class="sxs-lookup"><span data-stu-id="85721-106">This is accomplished by binding the <xref:System.Windows.Forms.BindingSource> component to your data source, and then binding the controls on your form to the <xref:System.Windows.Forms.BindingSource> component.</span></span> <span data-ttu-id="85721-107">Alle weiteren Interaktionen mit den Daten, einschließlich Navigieren, Sortieren, Filtern und Aktualisieren, werden durch Aufrufe an die <xref:System.Windows.Forms.BindingSource>-Komponente ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="85721-107">All further interaction with the data, including navigating, sorting, filtering, and updating, is accomplished with calls to the <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
 <span data-ttu-id="85721-108">Zweitens kann die <xref:System.Windows.Forms.BindingSource>-Komponente als Datenquelle mit starker Typisierung fungieren.</span><span class="sxs-lookup"><span data-stu-id="85721-108">Second, the <xref:System.Windows.Forms.BindingSource> component can act as a strongly typed data source.</span></span> <span data-ttu-id="85721-109">Wenn Sie der <xref:System.Windows.Forms.BindingSource>-Komponente einen Typ mit der <xref:System.Windows.Forms.BindingSource.Add%2A>-Methode hinzuzufügen, wird eine Liste dieses Typs erstellt.</span><span class="sxs-lookup"><span data-stu-id="85721-109">Adding a type to the <xref:System.Windows.Forms.BindingSource> component with the <xref:System.Windows.Forms.BindingSource.Add%2A> method creates a list of that type.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="85721-110">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="85721-110">In This Section</span></span>  
 [<span data-ttu-id="85721-111">Übersicht über die BindingSource-Komponente</span><span class="sxs-lookup"><span data-stu-id="85721-111">BindingSource Component Overview</span></span>](../../../../docs/framework/winforms/controls/bindingsource-component-overview.md)  
 <span data-ttu-id="85721-112">Stellt die allgemeinen Konzepte der <xref:System.Windows.Forms.BindingSource>-Komponente vor, mit deren Hilfe eine Datenquelle an ein Steuerelement gebunden werden kann.</span><span class="sxs-lookup"><span data-stu-id="85721-112">Introduces the general concepts of the <xref:System.Windows.Forms.BindingSource> component, which allows you to bind a data source to a control.</span></span>  
  
 [<span data-ttu-id="85721-113">Vorgehensweise: Binden von Windows Forms-Steuerelementen an DBNull-Datenbankwerte</span><span class="sxs-lookup"><span data-stu-id="85721-113">How to: Bind Windows Forms Controls to DBNull Database Values</span></span>](../../../../docs/framework/winforms/controls/how-to-bind-windows-forms-controls-to-dbnull-database-values.md)  
 <span data-ttu-id="85721-114">Veranschaulicht, wie ein <xref:System.DBNull>-Wert von der Datenquelle mit der <xref:System.Windows.Forms.BindingSource>-Komponente behandelt wird.</span><span class="sxs-lookup"><span data-stu-id="85721-114">Shows how to handle a <xref:System.DBNull> value from the data source using the <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
 [<span data-ttu-id="85721-115">Vorgehensweise: Sortieren und Filtern von ADO.NET-Daten mit der BindingSource-Komponente in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="85721-115">How to: Sort and Filter ADO.NET Data with the Windows Forms BindingSource Component</span></span>](../../../../docs/framework/winforms/controls/sort-and-filter-ado-net-data-with-wf-bindingsource-component.md)  
 <span data-ttu-id="85721-116">Veranschaulicht, wie mit der <xref:System.Windows.Forms.BindingSource>-Komponente Sortierungen und Filter auf angezeigte Daten angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="85721-116">Demonstrates using the <xref:System.Windows.Forms.BindingSource> component to apply sorts and filters to displayed data.</span></span>  
  
 [<span data-ttu-id="85721-117">Vorgehensweise: Binden an einen Webdienst mithilfe der BindingSource in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="85721-117">How to: Bind to a Web Service Using the Windows Forms BindingSource</span></span>](../../../../docs/framework/winforms/controls/how-to-bind-to-a-web-service-using-the-windows-forms-bindingsource.md)  
 <span data-ttu-id="85721-118">Veranschaulicht, wie mit der <xref:System.Windows.Forms.BindingSource>-Komponente Bindungen an einen Webdienst vorgenommen werden können.</span><span class="sxs-lookup"><span data-stu-id="85721-118">Shows how to use the <xref:System.Windows.Forms.BindingSource> component to bind to a Web service.</span></span>  
  
 [<span data-ttu-id="85721-119">Vorgehensweise: Behandeln von Fehlern und Ausnahmen in Zusammenhang mit der Datenbindung</span><span class="sxs-lookup"><span data-stu-id="85721-119">How to: Handle Errors and Exceptions that Occur with Databinding</span></span>](../../../../docs/framework/winforms/controls/how-to-handle-errors-and-exceptions-that-occur-with-databinding.md)  
 <span data-ttu-id="85721-120">Veranschaulicht, wie mit der <xref:System.Windows.Forms.BindingSource>-Komponente Fehler bei Datenbindungsvorgängen erfolgreich behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="85721-120">Demonstrates using the <xref:System.Windows.Forms.BindingSource> component to gracefully handle errors that occur in a data binding operation.</span></span>  
  
 [<span data-ttu-id="85721-121">Vorgehensweise: Binden eines Windows Forms-Steuerelements an einen Typ</span><span class="sxs-lookup"><span data-stu-id="85721-121">How to: Bind a Windows Forms Control to a Type</span></span>](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-type.md)  
 <span data-ttu-id="85721-122">Veranschaulicht die Verwendung einer <xref:System.Windows.Forms.BindingSource>-Komponente zum Binden an einen Typ.</span><span class="sxs-lookup"><span data-stu-id="85721-122">Demonstrates using a <xref:System.Windows.Forms.BindingSource> component to bind to a type.</span></span>  
  
 [<span data-ttu-id="85721-123">Vorgehensweise: Binden eines Windows Forms-Steuerelements an ein Factoryobjekt</span><span class="sxs-lookup"><span data-stu-id="85721-123">How to: Bind a Windows Forms Control to a Factory Object</span></span>](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-factory-object.md)  
 <span data-ttu-id="85721-124">Veranschaulicht die Verwendung einer <xref:System.Windows.Forms.BindingSource>-Komponente zum Binden an ein Factoryobjekt oder eine Methode.</span><span class="sxs-lookup"><span data-stu-id="85721-124">Demonstrates using a <xref:System.Windows.Forms.BindingSource> component to bind to a factory object or method.</span></span>  
  
 [<span data-ttu-id="85721-125">Vorgehensweise: Anpassen der Hinzufügung von Elementen mithilfe der BindingSource in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="85721-125">How to: Customize Item Addition with the Windows Forms BindingSource</span></span>](../../../../docs/framework/winforms/controls/how-to-customize-item-addition-with-the-windows-forms-bindingsource.md)  
 <span data-ttu-id="85721-126">Veranschaulicht die Verwendung einer <xref:System.Windows.Forms.BindingSource>-Komponente, um neue Elemente zu erstellen und sie einer Datenquelle hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="85721-126">Demonstrates using a <xref:System.Windows.Forms.BindingSource> component to create new items and add them to a data source.</span></span>  
  
 [<span data-ttu-id="85721-127">Vorgehensweise: Auslösen von Änderungsbenachrichtigungen mit der ResetItem-Methode einer BindingSource</span><span class="sxs-lookup"><span data-stu-id="85721-127">How to: Raise Change Notifications Using the BindingSource ResetItem Method</span></span>](../../../../docs/framework/winforms/controls/how-to-raise-change-notifications-using-the-bindingsource-resetitem-method.md)  
 <span data-ttu-id="85721-128">Veranschaulicht die Verwendung einer <xref:System.Windows.Forms.BindingSource>-Komponente zum Auslösen von Änderungsbenachrichtigungsereignissen für Datenquellen, die keine Änderungsbenachrichtigung unterstützen.</span><span class="sxs-lookup"><span data-stu-id="85721-128">Demonstrates using a <xref:System.Windows.Forms.BindingSource> component to raise change-notification events for data sources that do not support change notification.</span></span>  
  
 [<span data-ttu-id="85721-129">Vorgehensweise: Auslösen von Änderungsbenachrichtigungen mithilfe der BindingSource und der INotifyPropertyChanged-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="85721-129">How to: Raise Change Notifications Using a BindingSource and the INotifyPropertyChanged Interface</span></span>](../../../../docs/framework/winforms/controls/raise-change-notifications--bindingsource.md)  
 <span data-ttu-id="85721-130">Veranschaulicht die Verwendung eines Typs, der von <xref:System.ComponentModel.INotifyPropertyChanged> mit einem <xref:System.Windows.Forms.BindingSource>-Steuerelement erbt.</span><span class="sxs-lookup"><span data-stu-id="85721-130">Demonstrates how to use a type that inherits from the <xref:System.ComponentModel.INotifyPropertyChanged> with a <xref:System.Windows.Forms.BindingSource> control.</span></span>  
  
 [<span data-ttu-id="85721-131">Vorgehensweise: Kennzeichnen von Datenquellenaktualisierungen in einem Windows Forms-Steuerelement mithilfe der BindingSource</span><span class="sxs-lookup"><span data-stu-id="85721-131">How to: Reflect Data Source Updates in a Windows Forms Control with the BindingSource</span></span>](../../../../docs/framework/winforms/controls/reflect-data-source-updates-in-a-wf-control-with-the-bindingsource.md)  
 <span data-ttu-id="85721-132">Veranschaulicht, wie mit der <xref:System.Windows.Forms.BindingSource>-Komponente auf Änderungen in der Datenquelle reagiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="85721-132">Demonstrates how to respond to changes in the data source using the <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
 [<span data-ttu-id="85721-133">Vorgehensweise: Freigeben von gebundenen Daten in Formularen mithilfe der BindingSource-Komponente</span><span class="sxs-lookup"><span data-stu-id="85721-133">How to: Share Bound Data Across Forms Using the BindingSource Component</span></span>](../../../../docs/framework/winforms/controls/how-to-share-bound-data-across-forms-using-the-bindingsource-component.md)  
 <span data-ttu-id="85721-134">Veranschaulicht die Verwendung der <xref:System.Windows.Forms.BindingSource> zum Binden mehrerer Formulare an die gleiche Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="85721-134">Shows how to use the <xref:System.Windows.Forms.BindingSource> to bind multiple forms to the same data source.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="85721-135">Verweis</span><span class="sxs-lookup"><span data-stu-id="85721-135">Reference</span></span>  
 <xref:System.Windows.Forms.BindingSource>  
 <span data-ttu-id="85721-136">Enthält die Referenzdokumentation für die <xref:System.Windows.Forms.BindingSource>-Komponente.</span><span class="sxs-lookup"><span data-stu-id="85721-136">Provides reference documentation for the <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
 <xref:System.Windows.Forms.BindingNavigator>  
 <span data-ttu-id="85721-137">Enthält die Referenzdokumentation für das <xref:System.Windows.Forms.BindingNavigator>-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="85721-137">Provides reference documentation for the <xref:System.Windows.Forms.BindingNavigator> control.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="85721-138">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="85721-138">Related Sections</span></span>  
 [<span data-ttu-id="85721-139">Windows Forms-Datenbindung</span><span class="sxs-lookup"><span data-stu-id="85721-139">Windows Forms Data Binding</span></span>](../../../../docs/framework/winforms/windows-forms-data-binding.md)  
 <span data-ttu-id="85721-140">Enthält Links zu Themen, in denen die Architektur für die Datenbindung in Windows Forms beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="85721-140">Contains links to topics describing the Windows Forms data binding architecture.</span></span>  
  
 <span data-ttu-id="85721-141">Siehe auch [Binden von Steuerelementen an Daten in Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="85721-141">Also see [Bind controls to data in Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio).</span></span>
