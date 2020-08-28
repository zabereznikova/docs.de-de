---
title: Installieren der GPU-Unterstützung in Model Builder
description: So installieren Sie die GPU-Unterstützung in Model Builder.
ms.date: 08/18/2020
author: luisquintanilla
ms.author: luquinta
ms.topic: how-to
ms.openlocfilehash: ce629efa4c12a69f87196de35ebfe4331dc0800f
ms.sourcegitcommit: cbb19e56d48cf88375d35d0c27554d4722761e0d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/19/2020
ms.locfileid: "88608551"
---
# <a name="how-to-install-gpu-support-in-model-builder"></a><span data-ttu-id="353f7-103">Installieren der GPU-Unterstützung in Model Builder</span><span class="sxs-lookup"><span data-stu-id="353f7-103">How to install GPU support in Model Builder</span></span>

<span data-ttu-id="353f7-104">Hier erfahren Sie, wie Sie die GPU-Treiber installieren, um Ihre GPU mit Model Builder zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="353f7-104">Learn how to install the GPU drivers to use your GPU with Model Builder.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="353f7-105">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="353f7-105">Prerequisites</span></span>

- <span data-ttu-id="353f7-106">Model Builder-Erweiterung für Visual Studio –</span><span class="sxs-lookup"><span data-stu-id="353f7-106">Model Builder Visual Studio extension.</span></span> <span data-ttu-id="353f7-107">die Erweiterung ist ab Version 16.6.1 in Visual Studio integriert.</span><span class="sxs-lookup"><span data-stu-id="353f7-107">The extension is built into Visual Studio as of version 16.6.1.</span></span>
- <span data-ttu-id="353f7-108">[Model Builder-Erweiterung für Visual Studio für GPU-Unterstützung](https://marketplace.visualstudio.com/items?itemName=MLNET.ModelBuilderGPU)</span><span class="sxs-lookup"><span data-stu-id="353f7-108">[Model Builder Visual Studio GPU support extension](https://marketplace.visualstudio.com/items?itemName=MLNET.ModelBuilderGPU).</span></span>
- <span data-ttu-id="353f7-109">Mindestens eine CUDA-kompatible GPU –</span><span class="sxs-lookup"><span data-stu-id="353f7-109">At least one CUDA compatible GPU.</span></span> <span data-ttu-id="353f7-110">eine Liste der kompatiblen GPUs finden Sie im [NVIDIA-Leitfaden](https://developer.nvidia.com/cuda-gpus).</span><span class="sxs-lookup"><span data-stu-id="353f7-110">For a list of compatible GPUs, see [NVIDIA's guide](https://developer.nvidia.com/cuda-gpus).</span></span>
- <span data-ttu-id="353f7-111">NVIDIA-Entwicklerkonto –</span><span class="sxs-lookup"><span data-stu-id="353f7-111">NVIDIA developer account.</span></span> <span data-ttu-id="353f7-112">Falls Sie nicht über ein Abonnement verfügen, können Sie ein [kostenloses Konto erstellen](https://developer.nvidia.com/developer-program).</span><span class="sxs-lookup"><span data-stu-id="353f7-112">If you don't have one, [create a free account](https://developer.nvidia.com/developer-program).</span></span>

## <a name="install-dependencies"></a><span data-ttu-id="353f7-113">Installieren von Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="353f7-113">Install dependencies</span></span>

1. <span data-ttu-id="353f7-114">Installieren Sie [CUDA 10.0](https://developer.nvidia.com/cuda-10.0-download-archive).</span><span class="sxs-lookup"><span data-stu-id="353f7-114">Install [CUDA v10.0](https://developer.nvidia.com/cuda-10.0-download-archive).</span></span> <span data-ttu-id="353f7-115">Stellen Sie sicher, dass Sie CUDA 10.0 installieren – keine neuere Version.</span><span class="sxs-lookup"><span data-stu-id="353f7-115">Make sure you install CUDA v10.0, not any other newer version.</span></span> <span data-ttu-id="353f7-116">Es ist nicht möglich, mehrere Versionen von CUDA zu installieren.</span><span class="sxs-lookup"><span data-stu-id="353f7-116">You cannot have multiple versions of CUDA installed.</span></span>
1. <span data-ttu-id="353f7-117">Installieren Sie [cuDNN 7.6.4 für CUDA 10.0](https://developer.nvidia.com/rdp/cudnn-download).</span><span class="sxs-lookup"><span data-stu-id="353f7-117">Install [cuDNN v7.6.4 for CUDA 10.0](https://developer.nvidia.com/rdp/cudnn-download).</span></span> <span data-ttu-id="353f7-118">Es ist nicht möglich, mehrere Versionen von cuDNN zu installieren.</span><span class="sxs-lookup"><span data-stu-id="353f7-118">You cannot have multiple versions of cuDNN installed.</span></span> <span data-ttu-id="353f7-119">Laden Sie die ZIP-Datei für cuDNN 7.6.4 herunter, entpacken Sie diese, und kopieren Sie `<CUDNN_zip_files_path>\cuda\bin\cudnn64_7.dll` in `<YOUR_DRIVE>\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.0\bin`.</span><span class="sxs-lookup"><span data-stu-id="353f7-119">After downloading cuDNN v7.6.4 zip file and unpacking it, copy `<CUDNN_zip_files_path>\cuda\bin\cudnn64_7.dll` to `<YOUR_DRIVE>\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.0\bin`.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="353f7-120">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="353f7-120">Troubleshooting</span></span>

<span data-ttu-id="353f7-121">**Wie finde ich heraus, welche GPU ich habe?**</span><span class="sxs-lookup"><span data-stu-id="353f7-121">**How do I know what GPU I have?**</span></span>

<span data-ttu-id="353f7-122">Befolgen Sie diese Anweisungen:</span><span class="sxs-lookup"><span data-stu-id="353f7-122">Follow instructions provided:</span></span>

1. <span data-ttu-id="353f7-123">Klicken Sie mit der rechten Maustaste auf den Desktop.</span><span class="sxs-lookup"><span data-stu-id="353f7-123">Right-click on desktop</span></span>
1. <span data-ttu-id="353f7-124">Wenn im Kontextmenü „NVIDIA-Systemsteuerung“ oder „NVIDIA-Anzeige“ angezeigt wird, besitzen Sie eine NVIDIA-GPU.</span><span class="sxs-lookup"><span data-stu-id="353f7-124">If you see "NVIDIA Control Panel" or "NVIDIA Display" in the pop-up window, you have an NVIDIA GPU</span></span>
1. <span data-ttu-id="353f7-125">Klicken Sie im Kontextmenü auf „NVIDIA-Systemsteuerung“ oder „NVIDIA-Anzeige“.</span><span class="sxs-lookup"><span data-stu-id="353f7-125">Click on "NVIDIA Control Panel" or "NVIDIA Display" in the pop-up window</span></span>
1. <span data-ttu-id="353f7-126">Achten Sie auf die Option „Graphics Card Information“ (Grafikkarte).</span><span class="sxs-lookup"><span data-stu-id="353f7-126">Look at "Graphics Card Information"</span></span>
1. <span data-ttu-id="353f7-127">Dort wird der Name Ihrer NVIDIA-GPU angezeigt.</span><span class="sxs-lookup"><span data-stu-id="353f7-127">You will see the name of your NVIDIA GPU</span></span>

<span data-ttu-id="353f7-128">**Die NVIDIA-Systemsteuerung wird nicht angezeigt oder kann nicht geöffnet werden, obwohl eine NVIDIA-GPU eingebaut ist**</span><span class="sxs-lookup"><span data-stu-id="353f7-128">**I don't see NVIDIA Control Panel (or it fails to open) but I know I have an NVIDIA GPU.**</span></span>

1. <span data-ttu-id="353f7-129">Öffnen Sie den Geräte-Manager.</span><span class="sxs-lookup"><span data-stu-id="353f7-129">Open Device Manager</span></span>
1. <span data-ttu-id="353f7-130">Achten Sie auf die Option „Grafikkarten“.</span><span class="sxs-lookup"><span data-stu-id="353f7-130">Look at Display adapters</span></span>
1. <span data-ttu-id="353f7-131">Installieren Sie den geeigneten [Treiber](https://www.nvidia.com/drivers) für Ihre GPU.</span><span class="sxs-lookup"><span data-stu-id="353f7-131">Install appropriate [driver](https://www.nvidia.com/drivers) for your GPU.</span></span>
