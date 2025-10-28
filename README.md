# SGX-Test-Analysis

### Datasets
    论文的主要数据集
    1.SGX in Cloud/Final_SGX-in-cloud-chart.xlsx 从论坛爬取的SGX in Cloud相关的评论分析
    2.Test Code in SGX Projects/Repos_of_SGX_Proj.xlsx 从爬虫获取的repo分析得来，分析了repo是否含有测试代码，sgx测试代码（归纳sgx相关测试内容）
    3.Test Scenarios and Oracles/Final_TestScenarios.xlsx 从Intel SGX Developer Document中总结归纳的测试准则

### github_crawler
    爬取SGX仓库的测试代码
    1.SGXCrawler.py 爬取所有符合条件的SGX仓库，要求同时包含.edl文件和头文件sgx_urts.h，保存为json格式
    2.SGXAnalyzer.py 将json格式的文件写入到csv文件中
    3.SGXCrawlerEdl.py 爬取所有符合条件的SGX仓库，仅要求包含.edl文件，保存为json格式
    4.SGXCrawlerHead.py 爬取所有符合条件的SGX仓库，仅要求包含头文件sgx_urts.h，保存为json格式
    5.ResultCompare.py 对比1、3、4的结果，最后将：包含.edl但不包含sgx_urts.h，包含sgx_urts.h但不包含.edl的文件 筛选出来进行分析，查看爬虫筛选条件是否有漏洞

### Repos
    1.Repos.zip: 论文中涉及10个包含SGX测试代码的仓库的测试代码，每个仓库文件夹包含两个部分（sgx测试代码源文件、其他测试代码源文件）