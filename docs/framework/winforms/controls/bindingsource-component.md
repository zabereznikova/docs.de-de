---
title: BindingSource-Komponente
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [Windows Forms], Windows Forms
- Windows Forms, data binding control
- BindingSource component [Windows Forms]
ms.assetid: 3e2faf4c-f5b8-4fa6-9fbc-f59c37ec2fb9
ms.openlocfilehash: 54639edb512a8bc6c5909282d5e4c210439e2a6e
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57717595"
---
# <a name="bindingsource-component"></a><span data-ttu-id="1b126-102">BindingSource-Komponente</span><span class="sxs-lookup"><span data-stu-id="1b126-102">BindingSource Component</span></span>
<span data-ttu-id="1b126-103">Kapselt eine Datenquelle zum Binden an Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="1b126-103">Encapsulates a data source for binding to controls.</span></span>  
  
 <span data-ttu-id="1b126-104">Die <xref:System.Windows.Forms.BindingSource>-Komponente dient zwei Zwecken.</span><span class="sxs-lookup"><span data-stu-id="1b126-104">The <xref:System.Windows.Forms.BindingSource> component serves two purposes.</span></span> <span data-ttu-id="1b126-105">Erstens stellt sie eine Dereferenzierungsschicht bereit, wenn die Steuerelemente in einem Formular an Daten gebunden werden.</span><span class="sxs-lookup"><span data-stu-id="1b126-105">First, it provides a layer of indirection when binding the controls on a form to data.</span></span> <span data-ttu-id="1b126-106">Bei diesem Vorgang wird die <xref:System.Windows.Forms.BindingSource>-Komponente an die Datenquelle gebunden, und anschließend werden die Steuerelemente im Formular an die <xref:System.Windows.Forms.BindingSource>-Komponente gebunden.</span><span class="sxs-lookup"><span data-stu-id="1b126-106">This is accomplished by binding the <xref:System.Windows.Forms.BindingSource> component to your data source, and then binding the controls on your form to the <xref:System.Windows.Forms.BindingSource> component.</span></span> <span data-ttu-id="1b126-107">Alle weiteren Interaktionen mit den Daten, einschließlich Navigieren, Sortieren, Filtern und Aktualisieren, werden durch Aufrufe an die <xref:System.Windows.Forms.BindingSource>-Komponente ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="1b126-107">All further interaction with the data, including navigating, sorting, filtering, and updating, is accomplished with calls to the <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
 <span data-ttu-id="1b126-108">Zweitens kann die <xref:System.Windows.Forms.BindingSource>-Komponente als Datenquelle mit starker Typisierung fungieren.</span><span class="sxs-lookup"><span data-stu-id="1b126-108">Second, the <xref:System.Windows.Forms.BindingSource> component can act as a strongly typed data source.</span></span> <span data-ttu-id="1b126-109">Wenn Sie der <xref:System.Windows.Forms.BindingSource>-Komponente einen Typ mit der <xref:System.Windows.Forms.BindingSource.Add%2A>-Methode hinzuzufügen, wird eine Liste dieses Typs erstellt.</span><span class="sxs-lookup"><span data-stu-id="1b126-109">Adding a type to the <xref:System.Windows.Forms.BindingSource> component with the <xref:System.Windows.Forms.BindingSource.Add%2A> method creates a list of that type.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1b126-110">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="1b126-110">In This Section</span></span>  
 [<span data-ttu-id="1b126-111">Übersicht über die BindingSource-Komponente</span><span class="sxs-lookup"><span data-stu-id="1b126-111">BindingSource Component Overview</span></span>](bindingsource-component-overview.md)  
 <span data-ttu-id="1b126-112">Stellt die allgemeinen Konzepte der <xref:System.Windows.Forms.BindingSource>-Komponente vor, mit deren Hilfe eine Datenquelle an ein Steuerelement gebunden werden kann.</span><span class="sxs-lookup"><span data-stu-id="1b126-112">Introduces the general concepts of the <xref:System.Windows.Forms.BindingSource> component, which allows you to bind a data source to a control.</span></span>  
  
 [<span data-ttu-id="1b126-113">Vorgehensweise: Binden von Windows Forms-Steuerelementen an DBNull-Datenbankwerte</span><span class="sxs-lookup"><span data-stu-id="1b126-113">How to: Bind Windows Forms Controls to DBNull Database Values</span></span>](how-to-bind-windows-forms-controls-to-dbnull-database-values.md)  
 <span data-ttu-id="1b126-114">Veranschaulicht, wie ein <xref:System.DBNull>-Wert von der Datenquelle mit der <xref:System.Windows.Forms.BindingSource>-Komponente behandelt wird.</span><span class="sxs-lookup"><span data-stu-id="1b126-114">Shows how to handle a <xref:System.DBNull> value from the data source using the <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
 [<span data-ttu-id="1b126-115">Vorgehensweise: Sortieren und Filtern von ADO.NET-Daten mit der Windows Forms-BindingSource-Komponente</span><span class="sxs-lookup"><span data-stu-id="1b126-115">How to: Sort and Filter ADO.NET Data with the Windows Forms BindingSource Component</span></span>](sort-and-filter-ado-net-data-with-wf-bindingsource-component.md)  
 <span data-ttu-id="1b126-116">Veranschaulicht, wie mit der <xref:System.Windows.Forms.BindingSource>-Komponente Sortierungen und Filter auf angezeigte Daten angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="1b126-116">Demonstrates using the <xref:System.Windows.Forms.BindingSource> component to apply sorts and filters to displayed data.</span></span>  
  
 [<span data-ttu-id="1b126-117">Vorgehensweise: Binden Sie an einen Webdienst mithilfe der BindingSource in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1b126-117">How to: Bind to a Web Service Using the Windows Forms BindingSource</span></span>](how-to-bind-to-a-web-service-using-the-windows-forms-bindingsource.md)  
 <span data-ttu-id="1b126-118">Veranschaulicht, wie mit der <xref:System.Windows.Forms.BindingSource>-Komponente Bindungen an einen Webdienst vorgenommen werden können.</span><span class="sxs-lookup"><span data-stu-id="1b126-118">Shows how to use the <xref:System.Windows.Forms.BindingSource> component to bind to a Web service.</span></span>  
  
 [<span data-ttu-id="1b126-119">Vorgehensweise: Behandeln von Fehlern und Ausnahmen, die auftreten, mit der Datenbindung</span><span class="sxs-lookup"><span data-stu-id="1b126-119">How to: Handle Errors and Exceptions that Occur with Databinding</span></span>](how-to-handle-errors-and-exceptions-that-occur-with-databinding.md)  
 <span data-ttu-id="1b126-120">Veranschaulicht, wie mit der <xref:System.Windows.Forms.BindingSource>-Komponente Fehler bei Datenbindungsvorgängen erfolgreich behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="1b126-120">Demonstrates using the <xref:System.Windows.Forms.BindingSource> component to gracefully handle errors that occur in a data binding operation.</span></span>  
  
 [<span data-ttu-id="1b126-121">Vorgehensweise: Binden eines Windows Forms-Steuerelements an einen Typ</span><span class="sxs-lookup"><span data-stu-id="1b126-121">How to: Bind a Windows Forms Control to a Type</span></span>](how-to-bind-a-windows-forms-control-to-a-type.md)  
 <span data-ttu-id="1b126-122">Veranschaulicht die Verwendung einer <xref:System.Windows.Forms.BindingSource>-Komponente zum Binden an einen Typ.</span><span class="sxs-lookup"><span data-stu-id="1b126-122">Demonstrates using a <xref:System.Windows.Forms.BindingSource> component to bind to a type.</span></span>  
  
 [<span data-ttu-id="1b126-123">Vorgehensweise: Binden eines Windows Forms-Steuerelements an ein Factoryobjekt</span><span class="sxs-lookup"><span data-stu-id="1b126-123">How to: Bind a Windows Forms Control to a Factory Object</span></span>](how-to-bind-a-windows-forms-control-to-a-factory-object.md)  
 <span data-ttu-id="1b126-124">Veranschaulicht die Verwendung einer <xref:System.Windows.Forms.BindingSource>-Komponente zum Binden an ein Factoryobjekt oder eine Methode.</span><span class="sxs-lookup"><span data-stu-id="1b126-124">Demonstrates using a <xref:System.Windows.Forms.BindingSource> component to bind to a factory object or method.</span></span>  
  
 [<span data-ttu-id="1b126-125">Vorgehensweise: Anpassen der Hinzufügung mithilfe der BindingSource von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1b126-125">How to: Customize Item Addition with the Windows Forms BindingSource</span></span>](how-to-customize-item-addition-with-the-windows-forms-bindingsource.md)  
 <span data-ttu-id="1b126-126">Veranschaulicht die Verwendung einer <xref:System.Windows.Forms.BindingSource>-Komponente, um neue Elemente zu erstellen und sie einer Datenquelle hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="1b126-126">Demonstrates using a <xref:System.Windows.Forms.BindingSource> component to create new items and add them to a data source.</span></span>  
  
 [<span data-ttu-id="1b126-127">Vorgehensweise: Auslösen von Änderungsbenachrichtigungen mithilfe der BindingSource ResetItem-Methode</span><span class="sxs-lookup"><span data-stu-id="1b126-127">How to: Raise Change Notifications Using the BindingSource ResetItem Method</span></span>](how-to-raise-change-notifications-using-the-bindingsource-resetitem-method.md)  
 <span data-ttu-id="1b126-128">Veranschaulicht die Verwendung einer <xref:System.Windows.Forms.BindingSource>-Komponente zum Auslösen von Änderungsbenachrichtigungsereignissen für Datenquellen, die keine Änderungsbenachrichtigung unterstützen.</span><span class="sxs-lookup"><span data-stu-id="1b126-128">Demonstrates using a <xref:System.Windows.Forms.BindingSource> component to raise change-notification events for data sources that do not support change notification.</span></span>  
  
 [<span data-ttu-id="1b126-129">Vorgehensweise: Auslösen von Änderungsbenachrichtigungen mithilfe der BindingSource und der INotifyPropertyChanged-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1b126-129">How to: Raise Change Notifications Using a BindingSource and the INotifyPropertyChanged Interface</span></span>](raise-change-notifications--bindingsource.md)  
 <span data-ttu-id="1b126-130">Veranschaulicht die Verwendung eines Typs, der von <xref:System.ComponentModel.INotifyPropertyChanged> mit einem <xref:System.Windows.Forms.BindingSource>-Steuerelement erbt.</span><span class="sxs-lookup"><span data-stu-id="1b126-130">Demonstrates how to use a type that inherits from the <xref:System.ComponentModel.INotifyPropertyChanged> with a <xref:System.Windows.Forms.BindingSource> control.</span></span>  
  
 [<span data-ttu-id="1b126-131">Vorgehensweise: Datenquellenaktualisierungen Sie in einem Windows Forms-Steuerelement mit der BindingSource-Komponente</span><span class="sxs-lookup"><span data-stu-id="1b126-131">How to: Reflect Data Source Updates in a Windows Forms Control with the BindingSource</span></span>](reflect-data-source-updates-in-a-wf-control-with-the-bindingsource.md)  
 <span data-ttu-id="1b126-132">Veranschaulicht, wie mit der <xref:System.Windows.Forms.BindingSource>-Komponente auf Änderungen in der Datenquelle reagiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="1b126-132">Demonstrates how to respond to changes in the data source using the <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
 [<span data-ttu-id="1b126-133">Vorgehensweise: Freigeben von gebundenen Daten in Formularen mithilfe der BindingSource-Komponente</span><span class="sxs-lookup"><span data-stu-id="1b126-133">How to: Share Bound Data Across Forms Using the BindingSource Component</span></span>](how-to-share-bound-data-across-forms-using-the-bindingsource-component.md)  
 <span data-ttu-id="1b126-134">Veranschaulicht die Verwendung der <xref:System.Windows.Forms.BindingSource> zum Binden mehrerer Formulare an die gleiche Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="1b126-134">Shows how to use the <xref:System.Windows.Forms.BindingSource> to bind multiple forms to the same data source.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="1b126-135">Referenz</span><span class="sxs-lookup"><span data-stu-id="1b126-135">Reference</span></span>  
 <xref:System.Windows.Forms.BindingSource>  
 <span data-ttu-id="1b126-136">Enthält die Referenzdokumentation für die <xref:System.Windows.Forms.BindingSource>-Komponente.</span><span class="sxs-lookup"><span data-stu-id="1b126-136">Provides reference documentation for the <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
 <xref:System.Windows.Forms.BindingNavigator>  
 <span data-ttu-id="1b126-137">Enthält die Referenzdokumentation für das <xref:System.Windows.Forms.BindingNavigator>-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="1b126-137">Provides reference documentation for the <xref:System.Windows.Forms.BindingNavigator> control.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="1b126-138">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="1b126-138">Related Sections</span></span>  
 [<span data-ttu-id="1b126-139">Windows Forms-Datenbindung</span><span class="sxs-lookup"><span data-stu-id="1b126-139">Windows Forms Data Binding</span></span>](../windows-forms-data-binding.md)  
 <span data-ttu-id="1b126-140">Enthält Links zu Themen, in denen die Architektur für die Datenbindung in Windows Forms beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="1b126-140">Contains links to topics describing the Windows Forms data binding architecture.</span></span>  
  
 <span data-ttu-id="1b126-141">Siehe auch [Binden von Steuerelementen an Daten in Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="1b126-141">Also see [Bind controls to data in Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio).</span></span>
