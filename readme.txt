#代码调用关系核心包
mcanalysis-core:
	com.ai.bmg.mcanalysis.core.cfg //配置表（包括项目、项目仓库、项目模块等配置）DB操作相关类
	com.ai.bmg.mcanalysis.core.mcd //分析数据表（包括类、方法、业务组件等分析结果数据）DB操作相关类
	com.ai.bmg.mcanalysis.core.mcl //分析记录表（包括通知记录、更新记录、业务影响记录等数据）DB操作相关类
	com.ai.bmg.mcanalysis.core.mcm //分析通知表DB操作相关类
	com.ai.bmg.mcanalysis.core.mcm //系统管理表（包括用户、角色、系统参数等数据）DB操作相关类
	
#代码调用关系后台应用包	
mcanalysis-app:
	com.ai.bmg.mcanalysis.app.busialsis //业务分析
	com.ai.bmg.mcanalysis.app.codealsis //代码分析
	com.ai.bmg.mcanalysis.app.datastatistic //数据统计
	com.ai.bmg.mcanalysis.app.projectmgr //项目管理
	com.ai.bmg.mcanalysis.app.systemmgr //系统管理
	
#代码调用关系分析框架
mcanalysis-frame:
	com.ai.bmg.mcanalysis.bialsis //业务影响分析处理
	com.ai.bmg.mcanalysis.pnotice //通知调度
	com.ai.bmg.mcanalysis.ponline //项目上线通知处理
	com.ai.bmg.mcanalysis.pupdate //项目更新通知处理
	com.ai.bmg.mcanalysis.scalsis //项目分析
	
#代码调用关系分析定制包
mcanalysis-custom:
	com.ai.bmg.mcanalysis.frame.custom.csf //csf扩展分析
	com.ai.bmg.mcanalysis.frame.custom.page //page页面扩展分析
	com.ai.bmg.mcanalysis.frame.custom.rule //规则扩展分析
	
#mybatis相关代码生成工具
mcanalysis-mybatistools:
	com.ai.bmg.mcanaysis.mybatistools //mybatis or相关文件生成