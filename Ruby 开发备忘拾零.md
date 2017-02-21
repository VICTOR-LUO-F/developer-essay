# Ruby 开发备忘拾零

## 学习资料
### [Ruby on Rails 教程](https://railstutorial-china.org/book/)

## 常用函数和方法

### 产生随机字母字符串

    ('a'..'z').to_a.shuffle[0..7].join
    
### 产生随机数字字符串
    (0..9).to_a.shuffle[0..5].join

### 为字段添加唯一性索引

    class AddIndexToUsersEmail < ActiveRecord::Migration[5.0]
      def change
        add_index :users, :email, unique: true
      end
    end

### 特定运行环境的加载

    rails server --environment production/development/test

    rails db:migrate RAILS_ENV=production/development/test

    rails console production/development/test

其中，三个命令都可以使用参数 RAILS_ENV=production/development/test 的方式。

查看当前运行环境（在rails console 中）：

    Rails.env
    