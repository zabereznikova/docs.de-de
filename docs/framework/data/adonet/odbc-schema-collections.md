---
title: ODBC-Schemaauflistungen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1bb126a5-ceec-4649-a4bc-8aa19e801046
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: b8c31f4e8b1463c184c9a8ff1cf64808783f030d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="odbc-schema-collections"></a><span data-ttu-id="0b3da-102">ODBC-Schemaauflistungen</span><span class="sxs-lookup"><span data-stu-id="0b3da-102">ODBC Schema Collections</span></span>
<span data-ttu-id="0b3da-103">In diesem Abschnitt wird die Unterstützung von Schemaauflistungen für die ODBC-Treiber für Microsoft SQL Server, Oracle und Microsoft Jet diskutiert.</span><span class="sxs-lookup"><span data-stu-id="0b3da-103">This section discusses schema collection support for the ODBC drivers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-odbc-driver"></a><span data-ttu-id="0b3da-104">Microsoft SQL Server-ODBC-Treiber</span><span class="sxs-lookup"><span data-stu-id="0b3da-104">Microsoft SQL Server ODBC Driver</span></span>  
 <span data-ttu-id="0b3da-105">Der Microsoft SQL Server-ODBC-Treiber unterstützt die folgenden spezifischen schemaauflistungen zusätzlich zu den allgemeinen schemaauflistungen:</span><span class="sxs-lookup"><span data-stu-id="0b3da-105">The Microsoft SQL Server ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="0b3da-106">Tabellen</span><span class="sxs-lookup"><span data-stu-id="0b3da-106">Tables</span></span>  
  
-   <span data-ttu-id="0b3da-107">Indexes</span><span class="sxs-lookup"><span data-stu-id="0b3da-107">Indexes</span></span>  
  
-   <span data-ttu-id="0b3da-108">Columns</span><span class="sxs-lookup"><span data-stu-id="0b3da-108">Columns</span></span>  
  
-   <span data-ttu-id="0b3da-109">Verfahren</span><span class="sxs-lookup"><span data-stu-id="0b3da-109">Procedures</span></span>  
  
-   <span data-ttu-id="0b3da-110">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="0b3da-110">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="0b3da-111">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="0b3da-111">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="0b3da-112">Ansichten</span><span class="sxs-lookup"><span data-stu-id="0b3da-112">Views</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="0b3da-113">Tables und Views</span><span class="sxs-lookup"><span data-stu-id="0b3da-113">Tables and Views</span></span>  
  
|<span data-ttu-id="0b3da-114">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="0b3da-114">ColumnName</span></span>|<span data-ttu-id="0b3da-115">DataType</span><span class="sxs-lookup"><span data-stu-id="0b3da-115">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="0b3da-116">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="0b3da-116">TABLE_CAT</span></span>|<span data-ttu-id="0b3da-117">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-117">String</span></span>|  
|<span data-ttu-id="0b3da-118">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="0b3da-118">TABLE_SCHEM</span></span>|<span data-ttu-id="0b3da-119">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-119">String</span></span>|  
|<span data-ttu-id="0b3da-120">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="0b3da-120">TABLE_NAME</span></span>|<span data-ttu-id="0b3da-121">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-121">String</span></span>|  
|<span data-ttu-id="0b3da-122">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="0b3da-122">TABLE_TYPE</span></span>|<span data-ttu-id="0b3da-123">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-123">String</span></span>|  
|<span data-ttu-id="0b3da-124">REMARKS</span><span class="sxs-lookup"><span data-stu-id="0b3da-124">REMARKS</span></span>|<span data-ttu-id="0b3da-125">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-125">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="0b3da-126">Indexes</span><span class="sxs-lookup"><span data-stu-id="0b3da-126">Indexes</span></span>  
  
|<span data-ttu-id="0b3da-127">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="0b3da-127">ColumnName</span></span>|<span data-ttu-id="0b3da-128">DataType</span><span class="sxs-lookup"><span data-stu-id="0b3da-128">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="0b3da-129">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="0b3da-129">TABLE_CAT</span></span>|<span data-ttu-id="0b3da-130">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-130">String</span></span>|  
|<span data-ttu-id="0b3da-131">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="0b3da-131">TABLE_SCHEM</span></span>|<span data-ttu-id="0b3da-132">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-132">String</span></span>|  
|<span data-ttu-id="0b3da-133">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="0b3da-133">TABLE_NAME</span></span>|<span data-ttu-id="0b3da-134">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-134">String</span></span>|  
|<span data-ttu-id="0b3da-135">NON_UNIQUE</span><span class="sxs-lookup"><span data-stu-id="0b3da-135">NON_UNIQUE</span></span>|<span data-ttu-id="0b3da-136">Int16</span><span class="sxs-lookup"><span data-stu-id="0b3da-136">Int16</span></span>|  
|<span data-ttu-id="0b3da-137">INDEX_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="0b3da-137">INDEX_QUALIFIER</span></span>|<span data-ttu-id="0b3da-138">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-138">String</span></span>|  
|<span data-ttu-id="0b3da-139">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="0b3da-139">INDEX_NAME</span></span>|<span data-ttu-id="0b3da-140">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-140">String</span></span>|  
|<span data-ttu-id="0b3da-141">TYPE</span><span class="sxs-lookup"><span data-stu-id="0b3da-141">TYPE</span></span>|<span data-ttu-id="0b3da-142">Int16</span><span class="sxs-lookup"><span data-stu-id="0b3da-142">Int16</span></span>|  
|<span data-ttu-id="0b3da-143">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="0b3da-143">ORDINAL_POSITION</span></span>|<span data-ttu-id="0b3da-144">Int16</span><span class="sxs-lookup"><span data-stu-id="0b3da-144">Int16</span></span>|  
|<span data-ttu-id="0b3da-145">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="0b3da-145">COLUMN_NAME</span></span>|<span data-ttu-id="0b3da-146">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-146">String</span></span>|  
|<span data-ttu-id="0b3da-147">ASC_OR_DESC</span><span class="sxs-lookup"><span data-stu-id="0b3da-147">ASC_OR_DESC</span></span>|<span data-ttu-id="0b3da-148">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-148">String</span></span>|  
|<span data-ttu-id="0b3da-149">CARDINATLITY</span><span class="sxs-lookup"><span data-stu-id="0b3da-149">CARDINATLITY</span></span>|<span data-ttu-id="0b3da-150">Int32</span><span class="sxs-lookup"><span data-stu-id="0b3da-150">Int32</span></span>|  
|<span data-ttu-id="0b3da-151">PAGES</span><span class="sxs-lookup"><span data-stu-id="0b3da-151">PAGES</span></span>|<span data-ttu-id="0b3da-152">Int32</span><span class="sxs-lookup"><span data-stu-id="0b3da-152">Int32</span></span>|  
|<span data-ttu-id="0b3da-153">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="0b3da-153">FILTER_CONDITION</span></span>|<span data-ttu-id="0b3da-154">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-154">String</span></span>|  
|<span data-ttu-id="0b3da-155">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0b3da-155">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="0b3da-156">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-156">String</span></span>|  
|<span data-ttu-id="0b3da-157">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="0b3da-157">SS_DATA_TYPE</span></span>|<span data-ttu-id="0b3da-158">Byte</span><span class="sxs-lookup"><span data-stu-id="0b3da-158">Byte</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="0b3da-159">Columns</span><span class="sxs-lookup"><span data-stu-id="0b3da-159">Columns</span></span>  
  
|<span data-ttu-id="0b3da-160">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="0b3da-160">ColumnName</span></span>|<span data-ttu-id="0b3da-161">DataType</span><span class="sxs-lookup"><span data-stu-id="0b3da-161">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="0b3da-162">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="0b3da-162">TABLE_CAT</span></span>|<span data-ttu-id="0b3da-163">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-163">String</span></span>|  
|<span data-ttu-id="0b3da-164">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="0b3da-164">TABLE_SCHEM</span></span>|<span data-ttu-id="0b3da-165">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-165">String</span></span>|  
|<span data-ttu-id="0b3da-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="0b3da-166">TABLE_NAME</span></span>|<span data-ttu-id="0b3da-167">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-167">String</span></span>|  
|<span data-ttu-id="0b3da-168">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="0b3da-168">COLUMN_NAME</span></span>|<span data-ttu-id="0b3da-169">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-169">String</span></span>|  
|<span data-ttu-id="0b3da-170">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="0b3da-170">DATA_TYPE</span></span>|<span data-ttu-id="0b3da-171">Int16</span><span class="sxs-lookup"><span data-stu-id="0b3da-171">Int16</span></span>|  
|<span data-ttu-id="0b3da-172">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="0b3da-172">TYPE_NAME</span></span>|<span data-ttu-id="0b3da-173">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-173">String</span></span>|  
|<span data-ttu-id="0b3da-174">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="0b3da-174">COLUMN_SIZE</span></span>|<span data-ttu-id="0b3da-175">Int32</span><span class="sxs-lookup"><span data-stu-id="0b3da-175">Int32</span></span>|  
|<span data-ttu-id="0b3da-176">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="0b3da-176">BUFFER_LENGTH</span></span>|<span data-ttu-id="0b3da-177">Int32</span><span class="sxs-lookup"><span data-stu-id="0b3da-177">Int32</span></span>|  
|<span data-ttu-id="0b3da-178">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="0b3da-178">DECIMAL_DIGITS</span></span>|<span data-ttu-id="0b3da-179">Int16</span><span class="sxs-lookup"><span data-stu-id="0b3da-179">Int16</span></span>|  
|<span data-ttu-id="0b3da-180">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="0b3da-180">NUM_PREC_RADIX</span></span>|<span data-ttu-id="0b3da-181">Int16</span><span class="sxs-lookup"><span data-stu-id="0b3da-181">Int16</span></span>|  
|<span data-ttu-id="0b3da-182">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="0b3da-182">NULLABLE</span></span>|<span data-ttu-id="0b3da-183">Int16</span><span class="sxs-lookup"><span data-stu-id="0b3da-183">Int16</span></span>|  
|<span data-ttu-id="0b3da-184">REMARKS</span><span class="sxs-lookup"><span data-stu-id="0b3da-184">REMARKS</span></span>|<span data-ttu-id="0b3da-185">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-185">String</span></span>|  
|<span data-ttu-id="0b3da-186">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="0b3da-186">COLUMN_DEF</span></span>|<span data-ttu-id="0b3da-187">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-187">String</span></span>|  
|<span data-ttu-id="0b3da-188">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="0b3da-188">SQL_DATA_TYPE</span></span>|<span data-ttu-id="0b3da-189">Int16</span><span class="sxs-lookup"><span data-stu-id="0b3da-189">Int16</span></span>|  
|<span data-ttu-id="0b3da-190">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="0b3da-190">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="0b3da-191">Int16</span><span class="sxs-lookup"><span data-stu-id="0b3da-191">Int16</span></span>|  
|<span data-ttu-id="0b3da-192">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="0b3da-192">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="0b3da-193">Int32</span><span class="sxs-lookup"><span data-stu-id="0b3da-193">Int32</span></span>|  
|<span data-ttu-id="0b3da-194">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="0b3da-194">ORDINAL_POSITION</span></span>|<span data-ttu-id="0b3da-195">Int32</span><span class="sxs-lookup"><span data-stu-id="0b3da-195">Int32</span></span>|  
|<span data-ttu-id="0b3da-196">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="0b3da-196">IS_NULLABLE</span></span>|<span data-ttu-id="0b3da-197">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-197">String</span></span>|  
|<span data-ttu-id="0b3da-198">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0b3da-198">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="0b3da-199">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-199">String</span></span>|  
|<span data-ttu-id="0b3da-200">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0b3da-200">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="0b3da-201">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-201">String</span></span>|  
|<span data-ttu-id="0b3da-202">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="0b3da-202">SS_DATA_TYPE</span></span>|<span data-ttu-id="0b3da-203">Byte</span><span class="sxs-lookup"><span data-stu-id="0b3da-203">Byte</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="0b3da-204">Verfahren</span><span class="sxs-lookup"><span data-stu-id="0b3da-204">Procedures</span></span>  
  
|<span data-ttu-id="0b3da-205">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="0b3da-205">ColumnName</span></span>|<span data-ttu-id="0b3da-206">DataType</span><span class="sxs-lookup"><span data-stu-id="0b3da-206">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="0b3da-207">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="0b3da-207">PROCEDURE_CAT</span></span>|<span data-ttu-id="0b3da-208">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-208">String</span></span>|  
|<span data-ttu-id="0b3da-209">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="0b3da-209">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="0b3da-210">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-210">String</span></span>|  
|<span data-ttu-id="0b3da-211">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="0b3da-211">PROCEDURE_NAME</span></span>|<span data-ttu-id="0b3da-212">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-212">String</span></span>|  
|<span data-ttu-id="0b3da-213">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="0b3da-213">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="0b3da-214">Int32</span><span class="sxs-lookup"><span data-stu-id="0b3da-214">Int32</span></span>|  
|<span data-ttu-id="0b3da-215">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="0b3da-215">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="0b3da-216">Int32</span><span class="sxs-lookup"><span data-stu-id="0b3da-216">Int32</span></span>|  
|<span data-ttu-id="0b3da-217">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="0b3da-217">NUM_RESULT_SETS</span></span>|<span data-ttu-id="0b3da-218">Int32</span><span class="sxs-lookup"><span data-stu-id="0b3da-218">Int32</span></span>|  
|<span data-ttu-id="0b3da-219">REMARKS</span><span class="sxs-lookup"><span data-stu-id="0b3da-219">REMARKS</span></span>|<span data-ttu-id="0b3da-220">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-220">String</span></span>|  
|<span data-ttu-id="0b3da-221">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="0b3da-221">PROCEDURE_TYPE</span></span>|<span data-ttu-id="0b3da-222">Int16</span><span class="sxs-lookup"><span data-stu-id="0b3da-222">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="0b3da-223">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="0b3da-223">ProcedureColumns</span></span>  
  
|<span data-ttu-id="0b3da-224">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="0b3da-224">ColumnName</span></span>|<span data-ttu-id="0b3da-225">DataType</span><span class="sxs-lookup"><span data-stu-id="0b3da-225">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="0b3da-226">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="0b3da-226">PROCEDURE_CAT</span></span>|<span data-ttu-id="0b3da-227">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-227">String</span></span>|  
|<span data-ttu-id="0b3da-228">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="0b3da-228">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="0b3da-229">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-229">String</span></span>|  
|<span data-ttu-id="0b3da-230">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="0b3da-230">PROCEDURE_NAME</span></span>|<span data-ttu-id="0b3da-231">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-231">String</span></span>|  
|<span data-ttu-id="0b3da-232">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="0b3da-232">COLUMN_NAME</span></span>|<span data-ttu-id="0b3da-233">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-233">String</span></span>|  
|<span data-ttu-id="0b3da-234">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="0b3da-234">COLUMN_TYPE</span></span>|<span data-ttu-id="0b3da-235">Int16</span><span class="sxs-lookup"><span data-stu-id="0b3da-235">Int16</span></span>|  
|<span data-ttu-id="0b3da-236">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="0b3da-236">DATA_TYPE</span></span>|<span data-ttu-id="0b3da-237">Int16</span><span class="sxs-lookup"><span data-stu-id="0b3da-237">Int16</span></span>|  
|<span data-ttu-id="0b3da-238">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="0b3da-238">TYPE_NAME</span></span>|<span data-ttu-id="0b3da-239">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-239">String</span></span>|  
|<span data-ttu-id="0b3da-240">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="0b3da-240">COLUMN_SIZE</span></span>|<span data-ttu-id="0b3da-241">Int32</span><span class="sxs-lookup"><span data-stu-id="0b3da-241">Int32</span></span>|  
|<span data-ttu-id="0b3da-242">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="0b3da-242">BUFFER_LENGTH</span></span>|<span data-ttu-id="0b3da-243">Int32</span><span class="sxs-lookup"><span data-stu-id="0b3da-243">Int32</span></span>|  
|<span data-ttu-id="0b3da-244">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="0b3da-244">DECIMAL_DIGITS</span></span>|<span data-ttu-id="0b3da-245">Int16</span><span class="sxs-lookup"><span data-stu-id="0b3da-245">Int16</span></span>|  
|<span data-ttu-id="0b3da-246">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="0b3da-246">NUM_PREC_RADIX</span></span>|<span data-ttu-id="0b3da-247">Int16</span><span class="sxs-lookup"><span data-stu-id="0b3da-247">Int16</span></span>|  
|<span data-ttu-id="0b3da-248">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="0b3da-248">NULLABLE</span></span>|<span data-ttu-id="0b3da-249">Int16</span><span class="sxs-lookup"><span data-stu-id="0b3da-249">Int16</span></span>|  
|<span data-ttu-id="0b3da-250">REMARKS</span><span class="sxs-lookup"><span data-stu-id="0b3da-250">REMARKS</span></span>|<span data-ttu-id="0b3da-251">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-251">String</span></span>|  
|<span data-ttu-id="0b3da-252">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="0b3da-252">COLUMN_DEF</span></span>|<span data-ttu-id="0b3da-253">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-253">String</span></span>|  
|<span data-ttu-id="0b3da-254">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="0b3da-254">SQL_DATA_TYPE</span></span>|<span data-ttu-id="0b3da-255">Int16</span><span class="sxs-lookup"><span data-stu-id="0b3da-255">Int16</span></span>|  
|<span data-ttu-id="0b3da-256">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="0b3da-256">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="0b3da-257">Int16</span><span class="sxs-lookup"><span data-stu-id="0b3da-257">Int16</span></span>|  
|<span data-ttu-id="0b3da-258">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="0b3da-258">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="0b3da-259">Int32</span><span class="sxs-lookup"><span data-stu-id="0b3da-259">Int32</span></span>|  
|<span data-ttu-id="0b3da-260">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="0b3da-260">ORDINAL_POSITION</span></span>|<span data-ttu-id="0b3da-261">Int32</span><span class="sxs-lookup"><span data-stu-id="0b3da-261">Int32</span></span>|  
|<span data-ttu-id="0b3da-262">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="0b3da-262">IS_NULLABLE</span></span>|<span data-ttu-id="0b3da-263">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-263">String</span></span>|  
|<span data-ttu-id="0b3da-264">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0b3da-264">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="0b3da-265">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-265">String</span></span>|  
|<span data-ttu-id="0b3da-266">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0b3da-266">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="0b3da-267">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-267">String</span></span>|  
|<span data-ttu-id="0b3da-268">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="0b3da-268">SS_DATA_TYPE</span></span>|<span data-ttu-id="0b3da-269">Byte</span><span class="sxs-lookup"><span data-stu-id="0b3da-269">Byte</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="0b3da-270">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="0b3da-270">ProcedureParameters</span></span>  
  
|<span data-ttu-id="0b3da-271">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="0b3da-271">ColumnName</span></span>|<span data-ttu-id="0b3da-272">DataType</span><span class="sxs-lookup"><span data-stu-id="0b3da-272">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="0b3da-273">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="0b3da-273">PROCEDURE_CAT</span></span>|<span data-ttu-id="0b3da-274">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-274">String</span></span>|  
|<span data-ttu-id="0b3da-275">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="0b3da-275">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="0b3da-276">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-276">String</span></span>|  
|<span data-ttu-id="0b3da-277">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="0b3da-277">PROCEDURE_NAME</span></span>|<span data-ttu-id="0b3da-278">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-278">String</span></span>|  
|<span data-ttu-id="0b3da-279">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="0b3da-279">COLUMN_NAME</span></span>|<span data-ttu-id="0b3da-280">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-280">String</span></span>|  
|<span data-ttu-id="0b3da-281">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="0b3da-281">COLUMN_TYPE</span></span>|<span data-ttu-id="0b3da-282">Int16</span><span class="sxs-lookup"><span data-stu-id="0b3da-282">Int16</span></span>|  
|<span data-ttu-id="0b3da-283">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="0b3da-283">DATA_TYPE</span></span>|<span data-ttu-id="0b3da-284">Int16</span><span class="sxs-lookup"><span data-stu-id="0b3da-284">Int16</span></span>|  
|<span data-ttu-id="0b3da-285">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="0b3da-285">TYPE_NAME</span></span>|<span data-ttu-id="0b3da-286">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-286">String</span></span>|  
|<span data-ttu-id="0b3da-287">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="0b3da-287">COLUMN_SIZE</span></span>|<span data-ttu-id="0b3da-288">Int32</span><span class="sxs-lookup"><span data-stu-id="0b3da-288">Int32</span></span>|  
|<span data-ttu-id="0b3da-289">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="0b3da-289">BUFFER_LENGTH</span></span>|<span data-ttu-id="0b3da-290">Int32</span><span class="sxs-lookup"><span data-stu-id="0b3da-290">Int32</span></span>|  
|<span data-ttu-id="0b3da-291">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="0b3da-291">DECIMAL_DIGITS</span></span>|<span data-ttu-id="0b3da-292">Int16</span><span class="sxs-lookup"><span data-stu-id="0b3da-292">Int16</span></span>|  
|<span data-ttu-id="0b3da-293">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="0b3da-293">NUM_PREC_RADIX</span></span>|<span data-ttu-id="0b3da-294">Int16</span><span class="sxs-lookup"><span data-stu-id="0b3da-294">Int16</span></span>|  
|<span data-ttu-id="0b3da-295">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="0b3da-295">NULLABLE</span></span>|<span data-ttu-id="0b3da-296">Int16</span><span class="sxs-lookup"><span data-stu-id="0b3da-296">Int16</span></span>|  
|<span data-ttu-id="0b3da-297">REMARKS</span><span class="sxs-lookup"><span data-stu-id="0b3da-297">REMARKS</span></span>|<span data-ttu-id="0b3da-298">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-298">String</span></span>|  
|<span data-ttu-id="0b3da-299">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="0b3da-299">COLUMN_DEF</span></span>|<span data-ttu-id="0b3da-300">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-300">String</span></span>|  
|<span data-ttu-id="0b3da-301">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="0b3da-301">SQL_DATA_TYPE</span></span>|<span data-ttu-id="0b3da-302">Int16</span><span class="sxs-lookup"><span data-stu-id="0b3da-302">Int16</span></span>|  
|<span data-ttu-id="0b3da-303">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="0b3da-303">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="0b3da-304">Int16</span><span class="sxs-lookup"><span data-stu-id="0b3da-304">Int16</span></span>|  
|<span data-ttu-id="0b3da-305">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="0b3da-305">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="0b3da-306">Int32</span><span class="sxs-lookup"><span data-stu-id="0b3da-306">Int32</span></span>|  
|<span data-ttu-id="0b3da-307">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="0b3da-307">ORDINAL_POSITION</span></span>|<span data-ttu-id="0b3da-308">Int32</span><span class="sxs-lookup"><span data-stu-id="0b3da-308">Int32</span></span>|  
|<span data-ttu-id="0b3da-309">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="0b3da-309">IS_NULLABLE</span></span>|<span data-ttu-id="0b3da-310">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-310">String</span></span>|  
|<span data-ttu-id="0b3da-311">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0b3da-311">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="0b3da-312">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-312">String</span></span>|  
|<span data-ttu-id="0b3da-313">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0b3da-313">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="0b3da-314">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-314">String</span></span>|  
|<span data-ttu-id="0b3da-315">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="0b3da-315">SS_DATA_TYPE</span></span>|<span data-ttu-id="0b3da-316">Byte</span><span class="sxs-lookup"><span data-stu-id="0b3da-316">Byte</span></span>|  
  
## <a name="microsoft-oracle-odbc-driver"></a><span data-ttu-id="0b3da-317">Microsoft Oracle ODBC-Treiber</span><span class="sxs-lookup"><span data-stu-id="0b3da-317">Microsoft Oracle ODBC Driver</span></span>  
 <span data-ttu-id="0b3da-318">Microsoft SQL Server Oracle ODBC-Treiber unterstützt die folgenden spezifischen schemaauflistungen zusätzlich zu den allgemeinen schemaauflistungen:</span><span class="sxs-lookup"><span data-stu-id="0b3da-318">The Microsoft SQL Server Oracle ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="0b3da-319">Tabellen</span><span class="sxs-lookup"><span data-stu-id="0b3da-319">Tables</span></span>  
  
-   <span data-ttu-id="0b3da-320">Columns</span><span class="sxs-lookup"><span data-stu-id="0b3da-320">Columns</span></span>  
  
-   <span data-ttu-id="0b3da-321">Verfahren</span><span class="sxs-lookup"><span data-stu-id="0b3da-321">Procedures</span></span>  
  
-   <span data-ttu-id="0b3da-322">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="0b3da-322">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="0b3da-323">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="0b3da-323">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="0b3da-324">Ansichten</span><span class="sxs-lookup"><span data-stu-id="0b3da-324">Views</span></span>  
  
-   <span data-ttu-id="0b3da-325">Indexes</span><span class="sxs-lookup"><span data-stu-id="0b3da-325">Indexes</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="0b3da-326">Tables und Views</span><span class="sxs-lookup"><span data-stu-id="0b3da-326">Tables and Views</span></span>  
  
|<span data-ttu-id="0b3da-327">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="0b3da-327">ColumnName</span></span>|<span data-ttu-id="0b3da-328">DataType</span><span class="sxs-lookup"><span data-stu-id="0b3da-328">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="0b3da-329">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="0b3da-329">TABLE_QUALIFIER</span></span>|<span data-ttu-id="0b3da-330">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-330">String</span></span>|  
|<span data-ttu-id="0b3da-331">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="0b3da-331">TABLE_OWNER</span></span>|<span data-ttu-id="0b3da-332">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-332">String</span></span>|  
|<span data-ttu-id="0b3da-333">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="0b3da-333">TABLE_NAME</span></span>|<span data-ttu-id="0b3da-334">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-334">String</span></span>|  
|<span data-ttu-id="0b3da-335">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="0b3da-335">TABLE_TYPE</span></span>|<span data-ttu-id="0b3da-336">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-336">String</span></span>|  
|<span data-ttu-id="0b3da-337">REMARKS</span><span class="sxs-lookup"><span data-stu-id="0b3da-337">REMARKS</span></span>|<span data-ttu-id="0b3da-338">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-338">String</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="0b3da-339">Columns</span><span class="sxs-lookup"><span data-stu-id="0b3da-339">Columns</span></span>  
  
|<span data-ttu-id="0b3da-340">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="0b3da-340">ColumnName</span></span>|<span data-ttu-id="0b3da-341">DataType</span><span class="sxs-lookup"><span data-stu-id="0b3da-341">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="0b3da-342">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="0b3da-342">TABLE_QUALIFIER</span></span>|<span data-ttu-id="0b3da-343">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-343">String</span></span>|  
|<span data-ttu-id="0b3da-344">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="0b3da-344">TABLE_OWNER</span></span>|<span data-ttu-id="0b3da-345">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-345">String</span></span>|  
|<span data-ttu-id="0b3da-346">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="0b3da-346">TABLE_NAME</span></span>|<span data-ttu-id="0b3da-347">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-347">String</span></span>|  
|<span data-ttu-id="0b3da-348">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="0b3da-348">COLUMN_NAME</span></span>|<span data-ttu-id="0b3da-349">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-349">String</span></span>|  
|<span data-ttu-id="0b3da-350">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="0b3da-350">DATA_TYPE</span></span>|<span data-ttu-id="0b3da-351">Int16</span><span class="sxs-lookup"><span data-stu-id="0b3da-351">Int16</span></span>|  
|<span data-ttu-id="0b3da-352">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="0b3da-352">TYPE_NAME</span></span>|<span data-ttu-id="0b3da-353">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-353">String</span></span>|  
|<span data-ttu-id="0b3da-354">PRECISION</span><span class="sxs-lookup"><span data-stu-id="0b3da-354">PRECISION</span></span>|<span data-ttu-id="0b3da-355">Int32</span><span class="sxs-lookup"><span data-stu-id="0b3da-355">Int32</span></span>|  
|<span data-ttu-id="0b3da-356">LENGTH</span><span class="sxs-lookup"><span data-stu-id="0b3da-356">LENGTH</span></span>|<span data-ttu-id="0b3da-357">Int32</span><span class="sxs-lookup"><span data-stu-id="0b3da-357">Int32</span></span>|  
|<span data-ttu-id="0b3da-358">SCALE</span><span class="sxs-lookup"><span data-stu-id="0b3da-358">SCALE</span></span>|<span data-ttu-id="0b3da-359">Int16</span><span class="sxs-lookup"><span data-stu-id="0b3da-359">Int16</span></span>|  
|<span data-ttu-id="0b3da-360">RADIX</span><span class="sxs-lookup"><span data-stu-id="0b3da-360">RADIX</span></span>|<span data-ttu-id="0b3da-361">Int16</span><span class="sxs-lookup"><span data-stu-id="0b3da-361">Int16</span></span>|  
|<span data-ttu-id="0b3da-362">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="0b3da-362">NULLABLE</span></span>|<span data-ttu-id="0b3da-363">Int16</span><span class="sxs-lookup"><span data-stu-id="0b3da-363">Int16</span></span>|  
|<span data-ttu-id="0b3da-364">REMARKS</span><span class="sxs-lookup"><span data-stu-id="0b3da-364">REMARKS</span></span>|<span data-ttu-id="0b3da-365">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-365">String</span></span>|  
|<span data-ttu-id="0b3da-366">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="0b3da-366">ORDINAL_POSITION</span></span>|<span data-ttu-id="0b3da-367">Int32</span><span class="sxs-lookup"><span data-stu-id="0b3da-367">Int32</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="0b3da-368">Verfahren</span><span class="sxs-lookup"><span data-stu-id="0b3da-368">Procedures</span></span>  
  
|<span data-ttu-id="0b3da-369">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="0b3da-369">ColumnName</span></span>|<span data-ttu-id="0b3da-370">DataType</span><span class="sxs-lookup"><span data-stu-id="0b3da-370">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="0b3da-371">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="0b3da-371">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="0b3da-372">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-372">String</span></span>|  
|<span data-ttu-id="0b3da-373">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="0b3da-373">PROCEDURE_OWNER</span></span>|<span data-ttu-id="0b3da-374">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-374">String</span></span>|  
|<span data-ttu-id="0b3da-375">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="0b3da-375">PROCEDURE_NAME</span></span>|<span data-ttu-id="0b3da-376">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-376">String</span></span>|  
|<span data-ttu-id="0b3da-377">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="0b3da-377">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="0b3da-378">Int16</span><span class="sxs-lookup"><span data-stu-id="0b3da-378">Int16</span></span>|  
|<span data-ttu-id="0b3da-379">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="0b3da-379">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="0b3da-380">Int16</span><span class="sxs-lookup"><span data-stu-id="0b3da-380">Int16</span></span>|  
|<span data-ttu-id="0b3da-381">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="0b3da-381">NUM_RESULT_SETS</span></span>|<span data-ttu-id="0b3da-382">Int16</span><span class="sxs-lookup"><span data-stu-id="0b3da-382">Int16</span></span>|  
|<span data-ttu-id="0b3da-383">REMARKS</span><span class="sxs-lookup"><span data-stu-id="0b3da-383">REMARKS</span></span>|<span data-ttu-id="0b3da-384">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-384">String</span></span>|  
|<span data-ttu-id="0b3da-385">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="0b3da-385">PROCEDURE_TYPE</span></span>|<span data-ttu-id="0b3da-386">Int16</span><span class="sxs-lookup"><span data-stu-id="0b3da-386">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="0b3da-387">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="0b3da-387">ProcedureColumns</span></span>  
  
|<span data-ttu-id="0b3da-388">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="0b3da-388">ColumnName</span></span>|<span data-ttu-id="0b3da-389">DataType</span><span class="sxs-lookup"><span data-stu-id="0b3da-389">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="0b3da-390">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="0b3da-390">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="0b3da-391">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-391">String</span></span>|  
|<span data-ttu-id="0b3da-392">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="0b3da-392">PROCEDURE_OWNER</span></span>|<span data-ttu-id="0b3da-393">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-393">String</span></span>|  
|<span data-ttu-id="0b3da-394">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="0b3da-394">PROCEDURE_NAME</span></span>|<span data-ttu-id="0b3da-395">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-395">String</span></span>|  
|<span data-ttu-id="0b3da-396">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="0b3da-396">COLUMN_NAME</span></span>|<span data-ttu-id="0b3da-397">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-397">String</span></span>|  
|<span data-ttu-id="0b3da-398">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="0b3da-398">COLUMN_TYPE</span></span>|<span data-ttu-id="0b3da-399">Int16</span><span class="sxs-lookup"><span data-stu-id="0b3da-399">Int16</span></span>|  
|<span data-ttu-id="0b3da-400">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="0b3da-400">DATA_TYPE</span></span>|<span data-ttu-id="0b3da-401">Int16</span><span class="sxs-lookup"><span data-stu-id="0b3da-401">Int16</span></span>|  
|<span data-ttu-id="0b3da-402">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="0b3da-402">TYPE_NAME</span></span>|<span data-ttu-id="0b3da-403">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-403">String</span></span>|  
|<span data-ttu-id="0b3da-404">PRECISION</span><span class="sxs-lookup"><span data-stu-id="0b3da-404">PRECISION</span></span>|<span data-ttu-id="0b3da-405">Int32</span><span class="sxs-lookup"><span data-stu-id="0b3da-405">Int32</span></span>|  
|<span data-ttu-id="0b3da-406">LENGTH</span><span class="sxs-lookup"><span data-stu-id="0b3da-406">LENGTH</span></span>|<span data-ttu-id="0b3da-407">Int32</span><span class="sxs-lookup"><span data-stu-id="0b3da-407">Int32</span></span>|  
|<span data-ttu-id="0b3da-408">SCALE</span><span class="sxs-lookup"><span data-stu-id="0b3da-408">SCALE</span></span>|<span data-ttu-id="0b3da-409">Int16</span><span class="sxs-lookup"><span data-stu-id="0b3da-409">Int16</span></span>|  
|<span data-ttu-id="0b3da-410">RADIX</span><span class="sxs-lookup"><span data-stu-id="0b3da-410">RADIX</span></span>|<span data-ttu-id="0b3da-411">Int16</span><span class="sxs-lookup"><span data-stu-id="0b3da-411">Int16</span></span>|  
|<span data-ttu-id="0b3da-412">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="0b3da-412">NULLABLE</span></span>|<span data-ttu-id="0b3da-413">Int16</span><span class="sxs-lookup"><span data-stu-id="0b3da-413">Int16</span></span>|  
|<span data-ttu-id="0b3da-414">REMARKS</span><span class="sxs-lookup"><span data-stu-id="0b3da-414">REMARKS</span></span>|<span data-ttu-id="0b3da-415">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-415">String</span></span>|  
|<span data-ttu-id="0b3da-416">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="0b3da-416">OVERLOAD</span></span>|<span data-ttu-id="0b3da-417">Int32</span><span class="sxs-lookup"><span data-stu-id="0b3da-417">Int32</span></span>|  
|<span data-ttu-id="0b3da-418">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="0b3da-418">ORDINAL_POSITION</span></span>|<span data-ttu-id="0b3da-419">Int32</span><span class="sxs-lookup"><span data-stu-id="0b3da-419">Int32</span></span>|  
  
## <a name="microsoft-jet-odbc-driver"></a><span data-ttu-id="0b3da-420">Microsoft Jet ODBC-Treiber</span><span class="sxs-lookup"><span data-stu-id="0b3da-420">Microsoft Jet ODBC Driver</span></span>  
 <span data-ttu-id="0b3da-421">Der Microsoft Jet ODBC-Treiber unterstützt neben den allgemeinen Schemaauflistungen auch die folgenden spezifischen Schemaauflistungen:</span><span class="sxs-lookup"><span data-stu-id="0b3da-421">The Microsoft Jet ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="0b3da-422">Tabellen</span><span class="sxs-lookup"><span data-stu-id="0b3da-422">Tables</span></span>  
  
-   <span data-ttu-id="0b3da-423">Indexes</span><span class="sxs-lookup"><span data-stu-id="0b3da-423">Indexes</span></span>  
  
-   <span data-ttu-id="0b3da-424">Columns</span><span class="sxs-lookup"><span data-stu-id="0b3da-424">Columns</span></span>  
  
-   <span data-ttu-id="0b3da-425">Verfahren</span><span class="sxs-lookup"><span data-stu-id="0b3da-425">Procedures</span></span>  
  
-   <span data-ttu-id="0b3da-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="0b3da-426">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="0b3da-427">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="0b3da-427">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="0b3da-428">Ansichten</span><span class="sxs-lookup"><span data-stu-id="0b3da-428">Views</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="0b3da-429">Tables und Views</span><span class="sxs-lookup"><span data-stu-id="0b3da-429">Tables and Views</span></span>  
  
|<span data-ttu-id="0b3da-430">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="0b3da-430">ColumnName</span></span>|<span data-ttu-id="0b3da-431">DataType</span><span class="sxs-lookup"><span data-stu-id="0b3da-431">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="0b3da-432">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="0b3da-432">TABLE_QUALIFIER</span></span>|<span data-ttu-id="0b3da-433">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-433">String</span></span>|  
|<span data-ttu-id="0b3da-434">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="0b3da-434">TABLE_OWNER</span></span>|<span data-ttu-id="0b3da-435">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-435">String</span></span>|  
|<span data-ttu-id="0b3da-436">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="0b3da-436">TABLE_NAME</span></span>|<span data-ttu-id="0b3da-437">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-437">String</span></span>|  
|<span data-ttu-id="0b3da-438">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="0b3da-438">TABLE_TYPE</span></span>|<span data-ttu-id="0b3da-439">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-439">String</span></span>|  
|<span data-ttu-id="0b3da-440">REMARKS</span><span class="sxs-lookup"><span data-stu-id="0b3da-440">REMARKS</span></span>|<span data-ttu-id="0b3da-441">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-441">String</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="0b3da-442">Columns</span><span class="sxs-lookup"><span data-stu-id="0b3da-442">Columns</span></span>  
  
|<span data-ttu-id="0b3da-443">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="0b3da-443">ColumnName</span></span>|<span data-ttu-id="0b3da-444">DataType</span><span class="sxs-lookup"><span data-stu-id="0b3da-444">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="0b3da-445">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="0b3da-445">TABLE_QUALIFIER</span></span>|<span data-ttu-id="0b3da-446">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-446">String</span></span>|  
|<span data-ttu-id="0b3da-447">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="0b3da-447">TABLE_OWNER</span></span>|<span data-ttu-id="0b3da-448">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-448">String</span></span>|  
|<span data-ttu-id="0b3da-449">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="0b3da-449">TABLE_NAME</span></span>|<span data-ttu-id="0b3da-450">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-450">String</span></span>|  
|<span data-ttu-id="0b3da-451">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="0b3da-451">COLUMN_NAME</span></span>|<span data-ttu-id="0b3da-452">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-452">String</span></span>|  
|<span data-ttu-id="0b3da-453">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="0b3da-453">DATA_TYPE</span></span>|<span data-ttu-id="0b3da-454">Int16</span><span class="sxs-lookup"><span data-stu-id="0b3da-454">Int16</span></span>|  
|<span data-ttu-id="0b3da-455">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="0b3da-455">TYPE_NAME</span></span>|<span data-ttu-id="0b3da-456">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-456">String</span></span>|  
|<span data-ttu-id="0b3da-457">PRECISION</span><span class="sxs-lookup"><span data-stu-id="0b3da-457">PRECISION</span></span>|<span data-ttu-id="0b3da-458">Int32</span><span class="sxs-lookup"><span data-stu-id="0b3da-458">Int32</span></span>|  
|<span data-ttu-id="0b3da-459">LENGTH</span><span class="sxs-lookup"><span data-stu-id="0b3da-459">LENGTH</span></span>|<span data-ttu-id="0b3da-460">Int32</span><span class="sxs-lookup"><span data-stu-id="0b3da-460">Int32</span></span>|  
|<span data-ttu-id="0b3da-461">SCALE</span><span class="sxs-lookup"><span data-stu-id="0b3da-461">SCALE</span></span>|<span data-ttu-id="0b3da-462">Int16</span><span class="sxs-lookup"><span data-stu-id="0b3da-462">Int16</span></span>|  
|<span data-ttu-id="0b3da-463">RADIX</span><span class="sxs-lookup"><span data-stu-id="0b3da-463">RADIX</span></span>|<span data-ttu-id="0b3da-464">Int16</span><span class="sxs-lookup"><span data-stu-id="0b3da-464">Int16</span></span>|  
|<span data-ttu-id="0b3da-465">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="0b3da-465">NULLABLE</span></span>|<span data-ttu-id="0b3da-466">Int16</span><span class="sxs-lookup"><span data-stu-id="0b3da-466">Int16</span></span>|  
|<span data-ttu-id="0b3da-467">REMARKS</span><span class="sxs-lookup"><span data-stu-id="0b3da-467">REMARKS</span></span>|<span data-ttu-id="0b3da-468">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-468">String</span></span>|  
|<span data-ttu-id="0b3da-469">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="0b3da-469">ORDINAL_POSITION</span></span>|<span data-ttu-id="0b3da-470">Int32</span><span class="sxs-lookup"><span data-stu-id="0b3da-470">Int32</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="0b3da-471">Verfahren</span><span class="sxs-lookup"><span data-stu-id="0b3da-471">Procedures</span></span>  
  
|<span data-ttu-id="0b3da-472">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="0b3da-472">ColumnName</span></span>|<span data-ttu-id="0b3da-473">DataType</span><span class="sxs-lookup"><span data-stu-id="0b3da-473">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="0b3da-474">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="0b3da-474">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="0b3da-475">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-475">String</span></span>|  
|<span data-ttu-id="0b3da-476">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="0b3da-476">PROCEDURE_OWNER</span></span>|<span data-ttu-id="0b3da-477">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-477">String</span></span>|  
|<span data-ttu-id="0b3da-478">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="0b3da-478">PROCEDURE_NAME</span></span>|<span data-ttu-id="0b3da-479">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-479">String</span></span>|  
|<span data-ttu-id="0b3da-480">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="0b3da-480">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="0b3da-481">Int16</span><span class="sxs-lookup"><span data-stu-id="0b3da-481">Int16</span></span>|  
|<span data-ttu-id="0b3da-482">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="0b3da-482">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="0b3da-483">Int16</span><span class="sxs-lookup"><span data-stu-id="0b3da-483">Int16</span></span>|  
|<span data-ttu-id="0b3da-484">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="0b3da-484">NUM_RESULT_SETS</span></span>|<span data-ttu-id="0b3da-485">Int16</span><span class="sxs-lookup"><span data-stu-id="0b3da-485">Int16</span></span>|  
|<span data-ttu-id="0b3da-486">REMARKS</span><span class="sxs-lookup"><span data-stu-id="0b3da-486">REMARKS</span></span>|<span data-ttu-id="0b3da-487">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-487">String</span></span>|  
|<span data-ttu-id="0b3da-488">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="0b3da-488">PROCEDURE_TYPE</span></span>|<span data-ttu-id="0b3da-489">Int16</span><span class="sxs-lookup"><span data-stu-id="0b3da-489">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="0b3da-490">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="0b3da-490">ProcedureColumns</span></span>  
  
|<span data-ttu-id="0b3da-491">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="0b3da-491">ColumnName</span></span>|<span data-ttu-id="0b3da-492">DataType</span><span class="sxs-lookup"><span data-stu-id="0b3da-492">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="0b3da-493">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="0b3da-493">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="0b3da-494">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-494">String</span></span>|  
|<span data-ttu-id="0b3da-495">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="0b3da-495">PROCEDURE_OWNER</span></span>|<span data-ttu-id="0b3da-496">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-496">String</span></span>|  
|<span data-ttu-id="0b3da-497">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="0b3da-497">PROCEDURE_NAME</span></span>|<span data-ttu-id="0b3da-498">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-498">String</span></span>|  
|<span data-ttu-id="0b3da-499">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="0b3da-499">COLUMN_NAME</span></span>|<span data-ttu-id="0b3da-500">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-500">String</span></span>|  
|<span data-ttu-id="0b3da-501">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="0b3da-501">COLUMN_TYPE</span></span>|<span data-ttu-id="0b3da-502">Int16</span><span class="sxs-lookup"><span data-stu-id="0b3da-502">Int16</span></span>|  
|<span data-ttu-id="0b3da-503">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="0b3da-503">DATA_TYPE</span></span>|<span data-ttu-id="0b3da-504">Int16</span><span class="sxs-lookup"><span data-stu-id="0b3da-504">Int16</span></span>|  
|<span data-ttu-id="0b3da-505">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="0b3da-505">TYPE_NAME</span></span>|<span data-ttu-id="0b3da-506">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-506">String</span></span>|  
|<span data-ttu-id="0b3da-507">PRECISION</span><span class="sxs-lookup"><span data-stu-id="0b3da-507">PRECISION</span></span>|<span data-ttu-id="0b3da-508">Int32</span><span class="sxs-lookup"><span data-stu-id="0b3da-508">Int32</span></span>|  
|<span data-ttu-id="0b3da-509">LENGTH</span><span class="sxs-lookup"><span data-stu-id="0b3da-509">LENGTH</span></span>|<span data-ttu-id="0b3da-510">Int32</span><span class="sxs-lookup"><span data-stu-id="0b3da-510">Int32</span></span>|  
|<span data-ttu-id="0b3da-511">SCALE</span><span class="sxs-lookup"><span data-stu-id="0b3da-511">SCALE</span></span>|<span data-ttu-id="0b3da-512">Int16</span><span class="sxs-lookup"><span data-stu-id="0b3da-512">Int16</span></span>|  
|<span data-ttu-id="0b3da-513">RADIX</span><span class="sxs-lookup"><span data-stu-id="0b3da-513">RADIX</span></span>|<span data-ttu-id="0b3da-514">Int16</span><span class="sxs-lookup"><span data-stu-id="0b3da-514">Int16</span></span>|  
|<span data-ttu-id="0b3da-515">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="0b3da-515">NULLABLE</span></span>|<span data-ttu-id="0b3da-516">Int16</span><span class="sxs-lookup"><span data-stu-id="0b3da-516">Int16</span></span>|  
|<span data-ttu-id="0b3da-517">REMARKS</span><span class="sxs-lookup"><span data-stu-id="0b3da-517">REMARKS</span></span>|<span data-ttu-id="0b3da-518">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-518">String</span></span>|  
|<span data-ttu-id="0b3da-519">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="0b3da-519">OVERLOAD</span></span>|<span data-ttu-id="0b3da-520">Int32</span><span class="sxs-lookup"><span data-stu-id="0b3da-520">Int32</span></span>|  
|<span data-ttu-id="0b3da-521">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="0b3da-521">ORDINAL_POSITION</span></span>|<span data-ttu-id="0b3da-522">Int32</span><span class="sxs-lookup"><span data-stu-id="0b3da-522">Int32</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="0b3da-523">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="0b3da-523">ProcedureParameters</span></span>  
  
|<span data-ttu-id="0b3da-524">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="0b3da-524">ColumnName</span></span>|<span data-ttu-id="0b3da-525">DataType</span><span class="sxs-lookup"><span data-stu-id="0b3da-525">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="0b3da-526">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="0b3da-526">PROCEDURE_CAT</span></span>|<span data-ttu-id="0b3da-527">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-527">String</span></span>|  
|<span data-ttu-id="0b3da-528">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="0b3da-528">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="0b3da-529">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-529">String</span></span>|  
|<span data-ttu-id="0b3da-530">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="0b3da-530">PROCEDURE_NAME</span></span>|<span data-ttu-id="0b3da-531">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-531">String</span></span>|  
|<span data-ttu-id="0b3da-532">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="0b3da-532">COLUMN_NAME</span></span>|<span data-ttu-id="0b3da-533">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-533">String</span></span>|  
|<span data-ttu-id="0b3da-534">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="0b3da-534">COLUMN_TYPE</span></span>|<span data-ttu-id="0b3da-535">Int16</span><span class="sxs-lookup"><span data-stu-id="0b3da-535">Int16</span></span>|  
|<span data-ttu-id="0b3da-536">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="0b3da-536">DATA_TYPE</span></span>|<span data-ttu-id="0b3da-537">Int16</span><span class="sxs-lookup"><span data-stu-id="0b3da-537">Int16</span></span>|  
|<span data-ttu-id="0b3da-538">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="0b3da-538">TYPE_NAME</span></span>|<span data-ttu-id="0b3da-539">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-539">String</span></span>|  
|<span data-ttu-id="0b3da-540">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="0b3da-540">COLUMN_SIZE</span></span>|<span data-ttu-id="0b3da-541">Int32</span><span class="sxs-lookup"><span data-stu-id="0b3da-541">Int32</span></span>|  
|<span data-ttu-id="0b3da-542">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="0b3da-542">BUFFER_LENGTH</span></span>|<span data-ttu-id="0b3da-543">Int32</span><span class="sxs-lookup"><span data-stu-id="0b3da-543">Int32</span></span>|  
|<span data-ttu-id="0b3da-544">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="0b3da-544">DECIMAL_DIGITS</span></span>|<span data-ttu-id="0b3da-545">Int16</span><span class="sxs-lookup"><span data-stu-id="0b3da-545">Int16</span></span>|  
|<span data-ttu-id="0b3da-546">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="0b3da-546">NUM_PREC_RADIX</span></span>|<span data-ttu-id="0b3da-547">Int16</span><span class="sxs-lookup"><span data-stu-id="0b3da-547">Int16</span></span>|  
|<span data-ttu-id="0b3da-548">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="0b3da-548">NULLABLE</span></span>|<span data-ttu-id="0b3da-549">Int16</span><span class="sxs-lookup"><span data-stu-id="0b3da-549">Int16</span></span>|  
|<span data-ttu-id="0b3da-550">REMARKS</span><span class="sxs-lookup"><span data-stu-id="0b3da-550">REMARKS</span></span>|<span data-ttu-id="0b3da-551">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-551">String</span></span>|  
|<span data-ttu-id="0b3da-552">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="0b3da-552">COLUMN_DEF</span></span>|<span data-ttu-id="0b3da-553">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-553">String</span></span>|  
|<span data-ttu-id="0b3da-554">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="0b3da-554">SQL_DATA_TYPE</span></span>|<span data-ttu-id="0b3da-555">Int16</span><span class="sxs-lookup"><span data-stu-id="0b3da-555">Int16</span></span>|  
|<span data-ttu-id="0b3da-556">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="0b3da-556">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="0b3da-557">Int16</span><span class="sxs-lookup"><span data-stu-id="0b3da-557">Int16</span></span>|  
|<span data-ttu-id="0b3da-558">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="0b3da-558">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="0b3da-559">Int32</span><span class="sxs-lookup"><span data-stu-id="0b3da-559">Int32</span></span>|  
|<span data-ttu-id="0b3da-560">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="0b3da-560">ORDINAL_POSITION</span></span>|<span data-ttu-id="0b3da-561">Int32</span><span class="sxs-lookup"><span data-stu-id="0b3da-561">Int32</span></span>|  
|<span data-ttu-id="0b3da-562">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="0b3da-562">IS_NULLABLE</span></span>|<span data-ttu-id="0b3da-563">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0b3da-563">String</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0b3da-564">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0b3da-564">See Also</span></span>  
 [<span data-ttu-id="0b3da-565">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="0b3da-565">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
