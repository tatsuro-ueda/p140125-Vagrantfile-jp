# -*- mode: ruby -*-
# vi: set ft=ruby :

# VagrantfileのAPIや文法のバージョン。よくわからないときは触らないでください。
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  # すべてのVagrantの設定はここで行われる。
  # 最も一般的な設定は以下に書かれている。
  # すべてのリファレンスは、
  # vagrantup.comにあるオンライン・ドキュメントを見てください。

  # すべてのVagrant仮想環境は作り直すためにボックスを必要とする。
  config.vm.box = "base"

  # ユーザのシステムにまだ存在しない「config.vm.box」ボックスをダウンロードするURL
  # config.vm.box_url = "http://domain.com/path/to/above.box"

  # ホストマシンのポートからアクセスすることができる特別な、
  # ポートフォワードされたポートをつくる
  # 以下の例では、「localhost:8080」にアクセスすることで
  # ゲストマシンの80番ポートにアクセスする。
  # config.vm.network :forwarded_port, guest: 80, host: 8080

  # 特定のIPアドレスを使って
  # ホストマシンからだけアクセスできるプライベート・ネットワークを作る
  config.vm.network :private_network, ip: "192.168.33.10"

  # ブリッジされたネットワークに適合するパブリック・ネットワークをつくる
  # ブリッジされたネットワークは、
  # マシンをあたかも別の物理機器があなたのネットワークかのように見せる
  # config.vm.network :public_network

  # もし「true」にすると、
  # すべてのSSH接続はエージェント・フォワーディング（？）を可能にする。
  # デフォルトでは「false」になっている。
  # config.ssh.forward_agent = true

  # 別のフォルダをゲストマシンと共有する。
  # 1番目の引数は、ホスト上の実際のパスである。
  # 2番目の引数は、ゲスト上にマウントされるフォルダのパスである。
  # 3番目の引数は、もし必要になれば使うことのできるオプションである。
  # config.vm.synced_folder "../data", "/vagrant_data"

  # 特別なプロバイダ（VirtualBoxとかParallels）の設定をすることで、
  # Vagrantのための様々な背後で動いているプロバイダに最適化できる。
  # プロバイダ固有のオプションを変えることができる。
  # 以下はVirtualBox用の例：
  #
  # config.vm.provider :virtualbox do |vb|
  #   # ヘッドレス・モード（ターミナルのみ）では起動しない
  #   vb.gui = true
  #
  #   # VMをカスタマイズするためにVBoxManageを使う。 
  #   # 例えばメモリを変えるようなときには、
  #   # VMをカスタマイズするのにVBoxManageを使う。
  #   # 例えばメモリを変えるには以下のようにする：
  #   vb.customize ["modifyvm", :id, "--memory", "1024"]
  # end
  #
  # 使うことのできるオプションについてさらに知りたいことがあれば、
  # あなたが使っているプロバイダのためのドキュメントを見てください。

  # スタンドアローンのPuppetで配置できます。
  # Puppetのマニフェストは
  # このVagrantfileからの相対パスのディレクトリの中にあります。
  # まずマニフェスト・ディレクトリをつくり、
  # 次にmanifests_pathのディレクトリの中のbase.ppファイルの中に
  # マニフェストをつくらなければなりません。
  # 
  # 以下はその日のメッセージ（？）を配置するためのPuppetのマニフェストの例です：
  #
  # # group { "puppet":
  # #   ensure => "present",
  # # }
  # #
  # # File { owner => 0, group => 0, mode => 0644 }
  # #
  # # file { '/etc/motd':
  # #   content => "Welcome to your Vagrant-built virtual machine!
  # #               Managed by Puppet.\n"
  # # }
  #
  # config.vm.provision :puppet do |puppet|
  #   puppet.manifests_path = "manifests"
  #   puppet.manifest_file  = "site.pp"
  # end

  # chef soloで配置するには、cookbookの
  # path、roles_path、data_bags_path（すべてVagrantfileからの相対パス）
  # を特定し、レシピやロールを追加します。
  #
  # config.vm.provision :chef_solo do |chef|
  #   chef.cookbooks_path = "../my-recipes/cookbooks"
  #   chef.roles_path = "../my-recipes/roles"
  #   chef.data_bags_path = "../my-recipes/data_bags"
  #   chef.add_recipe "mysql"
  #   chef.add_role "web"
  #
  #   # カスタムなJSON属性を指定することもできます：
  #   chef.json = { :mysql_password => "foo" }
  # end

  # chefサーバで配置するには、
  # chefサーバのURLとバリデーションキー（？）のパス（すべてVagrantfileからの相対パス）
  # を指定しなければなりません。
  # 
  # OpscodeプラットフォームはHTTPSを使います。
  # 前述したURLのなかにあるORGNAMEとバリデーションキーの代わりに
  # あなたの組織名を記述してください。
  #
  # もしあなたが自分のChefサーバを持っているのなら、
  # 適切なURLを使ってください。
  # そのURLは、あなたの設定によってはHTTPSの代わりにHTTPかもしれません。
  # バリデーションキーもvalidation.pemに変えてください。
  #
  # config.vm.provision :chef_client do |chef|
  #   chef.chef_server_url = "https://api.opscode.com/organizations/ORGNAME"
  #   chef.validation_key_path = "ORGNAME-validator.pem"
  # end
  #
  # もしあなたがOpscodeプラットフォームを使っているのなら、
  # あなたのvalidatorクライアント（？）はORGNAME-validatorです。
  # ORGNAMEの部分をあなたの組織名に変えてください。
  #
  # もしあなたが自分のChefサーバを持っているのなら、
  # デフォルトのvalidationクライアント（？）の名前はchef-validatorです。
  # あなたが設定を変えていなければ、ですが。
  #
  #   chef.validation_client_name = "ORGNAME-validator"

  config.proxy.http     = "http://proxy1.screen.co.jp:8080"
  config.proxy.https    = "http://proxy1.screen.co.jp:8080"
end
