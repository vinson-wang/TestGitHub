GitHub����
1.��װgit for windows�����ص�ַ�� https://git-for-windows.github.io/
2.��GitBash�����������Ϣ
git config --global user.name "�û���"
git config --global user.email "����"
3.����SSH��Կ
�鿴�Ƿ��Ѿ�����SSH��Կ:cd ~/.ssh
û����������Կ��ssh-keygen -t rsa �CC "email"���������س�����������Ϊ�գ��ɹ�����C:\Users\Administrator\.ssh�еõ��������ļ�:id_rsa��id_rsa.pub��
4.��SSH ��Կ�ϴ���GitHub��
  ����https://github.com/settings/keysҳ�棬����µ�SSH Key, Title���ֿ����ȡ,������ʶ���õ��ĸ���������Ϊ���п����ڶ�̨�����Ϸ���GitHub������ÿ̨�����϶�Ҫ���� SSH Key���ϴ���GitHub�ϡ�Key�ǽ�id_rsa.pub �е�ȫ�����ݿ������ı����С�
5.�����Ƿ������SSH���ӵ�GitHub��:ssh -T git@github.com
  The authenticity of host ��github.com (207.97.227.239)�� can��t be established.
RSA key fingerprint is 16:27:ac:a5:76:28:2d:36:63:1b:56:4d:eb:df:a6:48.
Are you sure you want to continue connecting (yes/no)? yes
Warning: Permanently added ��github.com,207.97.227.239�� (RSA) to the list of known hosts.
ERROR: Hi tekkub! You��ve successfully authenticated, but GitHub does not provide shell access
Connection to github.com closed.
  ����������Ϣ���ʾ���ӳɹ���
6.Clone GitHub�ϵĲֿ⵽����
I.SSH�ķ�ʽ
��$��ִ������:git clone git@github.com:�˺�/�ֿ���.git
�����˺ž������Լ���GitHub��ע��ĵ�¼�û������ֿ�������repository����Ϊ�����ǲ���SSH�ķ�ʽ����Clone����Ϊ�Ѿ���SSH Key���ݵ�GitHub�ϣ�������صĲ����Ͳ��������û����������ˡ�
II.http�ķ�ʽ
Ҳ���Բ���https�ķ�ʽ����Clone:git clone https://github.com/�˺�/�ֿ���.git
ִ���������Ҳ�ܰ�GitHub�ϵĲֿ��������ص����أ����������Ҫ���в��������漰���Է�����push���ʱ����Ҫ�����û��������롣
7.���Բ���Ҫ�ύ���ļ����ļ���
�ڲֿ��Ŀ¼�´�������Ϊ��.gitignore�����ļ���д�벻��Ҫ���ļ��������ļ���ÿ��Ԫ��ռһ�м��ɣ��磺
node_modules
bin
*.config
8.GitHubԶ�̲���
  
I��git remote
git remote:�г�����Զ������(origin)��
git remote �Cv:�鿴Զ��������ַ��
git remote show <������>:�鿴��������ϸ��Ϣ��
git remote add <������> <��ַ>:���Զ��������
git remote rm <������>:ɾ��Զ��������
git remote rename <ԭ������> <��������>:�޸�Զ���������ơ�
II��git fetch
git fetch <Զ��������>:ȡ��Զ���������з�֧�ĸ��£�
git fetch <Զ��������> <��֧��>:ȡ���ض���֧�ĸ��£�
��ȡ��origin������master��֧:git fetch origin masier��
  ��Զ�̷�֧�Ļ����ϴ���һ���·�֧:
��:git checkout �Cb newbranch origon/master����ʾ��Զ�̷�֧origon/master�Ļ����ϣ�����һ���·�֧��
�ڱ��ط�֧�Ϻϲ�Զ�̷�֧:
��:git merge origin/master �� git rebase origin/master����ʾ�ڵ�ǰ��֧�ϣ��ϲ�Զ�̷�֧origin/master��
III��git pull
git pull <Զ��������> <Զ�̷�֧��>:<���ط�֧��>:ȡ��Զ������ĳ����֧�ĸ��£����뱾�ص�ָ����֧�ϲ�;
��:git pull origin next:master����ʾȡ��origin������next��֧���뱾��master��֧�ϲ���
���Զ�̷�֧���뵱ǰ��֧�ϲ���ð�ź������ݿ�ʡ��:git pull origin next��ʵ���ϣ����������ͬ��������git fetch������git merge:��git fetch origin��Ȼ��git merge origin/nex��
IV��git tracking
git���Զ��ڱ��ط�֧��Զ�̷�֧֮�䣬����һ��׷�ٹ�ϵ��tracking�������磬��git clone��ʱ�����б��ط�֧Ĭ����Զ��������ͬ����֧������׷�ٹ�ϵ��Ҳ����˵�����ص�master��֧�Զ�"׷��"origin/master��֧��
Git�ֶ�����׷�ٹ�ϵ: git branch --set-upstream master origin/next
��������ָ��mater��֧׷��origin/next��֧��
�����ǰ��֧��Զ�̷�֧����׷�ٹ�ϵ���Ϳ���ʡ��Զ�̷�֧��:git pull origin��
���������ʾ�����صĵ�ǰ��֧�Զ����Ӧ��origin����"׷�ٷ�֧"���кϲ���
�����ǰ��ֻ֧��һ��׷�ٷ�֧����Զ��������������ʡ��:git pull��
���������ʾ����ǰ��֧�Զ���Ψһһ��׷�ٷ�֧���кϲ���
����ϲ���Ҫ����rebaseģʽ������ʹ��--rebaseѡ�
git pull --rebase <Զ��������> <Զ�̷�֧��>:<���ط�֧��>��
V��git push
git push <Զ��������> <���ط�֧��>:<Զ�̷�֧��>:�����ط�֧�ĸ��£����͵�Զ��������
ע�⣬��֧����˳���д����<��Դ��>:<Ŀ�ĵ�>������git pull��<Զ�̷�֧>:<���ط�֧>����git push��<���ط�֧>:<Զ�̷�֧>��
���ʡ��Զ�̷�֧�������ʾ�����ط�֧������֮����"׷�ٹ�ϵ"��Զ�̷�֧��ͨ������ͬ�����������Զ�̷�֧�����ڣ���ᱻ�½���
��git push origin master����ʾ�����ص�master��֧���͵�origin������master��֧��������߲����ڣ���ᱻ�½���
���ʡ�Ա��ط�֧�������ʾɾ��ָ����Զ�̷�֧����Ϊ���ͬ������һ���յı��ط�֧��Զ�̷�֧��git push origin :master��ͬ��git push origin --delete master����ʾɾ��origin������master��֧��
�����ǰ��֧��Զ�̷�֧֮�����׷�ٹ�ϵ���򱾵ط�֧��Զ�̷�֧������ʡ�ԣ�git push origin����ʾ����ǰ��֧���͵�origin�����Ķ�Ӧ��֧��
�����ǰ��ֻ֧��һ��׷�ٷ�֧����ô������������ʡ�ԣ�git push��
�����ǰ��֧������������׷�ٹ�ϵ�������ʹ��-uѡ��ָ��һ��Ĭ����������������Ϳ��Բ����κβ���ʹ��git push��git push -u origin master����ʾ�����ص�master��֧���͵�origin������ͬʱָ��originΪĬ������������Ϳ��Բ����κβ���ʹ��git push�ˣ�
git push --all origin����ʾ�����б��ط�֧�����͵�origin���������Զ�������İ汾�ȱ��ذ汾�£�����ʱgit�ᱨ��Ҫ�����ڱ�����git pull�ϲ����죬Ȼ�������͵�Զ����������ʱ�������һ��Ҫ���ͣ�����ʹ��--forceѡ�git push --force origin��ʹ��--forceѡ��������Զ�������ϸ��µİ汾�����ǣ��������ȷ��Ҫ������������Ӧ�þ�������ʹ��--forceѡ�
9.GitHub��������
  git branch:�鿴���ط�֧
  git branch -r:�鿴Զ�̷�֧
  git branch -a:�鿴���з�֧
  git branch <��֧��>:�������ط�֧��ע�ⴴ���󲻻��Զ��л�Ϊ��ǰ��֧
  git checkout <��֧��>:�л���֧
  git checkout -b<��֧��>:�����·�֧�������л����·�֧
git branch -d <��֧��>:ɾ���Ѿ�����ϲ��ķ�֧��δ�ϲ��ķ�֧�޷�ɾ��
git branch -D <��֧��>:ǿ��ɾ����֧
git merge <��֧��>:���÷�֧�뵱ǰ��֧�ϲ�
git push origin <��֧��>:������÷�֧������ͬ��Զ�̷�֧
git push origin:<��֧��>:ɾ��Զ�̷�֧
git status:�鿴��ǰ״̬
git add �CA:�ύ���б仯
git add -u:�ύ���޸ĺͱ�ɾ��(�ļ������������ļ�
git add .:�ύ���ļ��ͱ��޸��ļ�����������ɾ���ļ�
git commit -m ��ע�͡�:ֻ���ύ��ӵ����������ļ�(ֻ�ύ��ӵ�)
git commit -a -m ��ע�͡�:�ύ�޸Ĺ�������û����ӵ����������ļ�(�޸Ĺ��ľ����ύ)
git log:�鿴commit����־��Ϣ
git diff <�ļ���>:�鿴��δ�ݴ�ĸ���
git rm <�ļ���>:�Ƴ��ļ�(���ݴ����͹�������ɾ��)
git rm -cached<�ļ���>:�Ƴ��ļ�(ֻ���ݴ�����ɾ��)
git rm -f <�ļ���>:ǿ���Ƴ��޸ĺ��ļ�(���ݴ����͹�������ɾ��)
  


  








