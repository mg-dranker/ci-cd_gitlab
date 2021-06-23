FROM centos:centos7

RUN curl -L https://packages.gitlab.com/install/repositories/runner/gitlab-runner/script.rpm.sh | bash
RUN GITLAB_RUNNER_DISABLE_SKEL=true yum install gitlab-runner -y

CMD gitlab-runner register \
-u http://gitlab/ci \
-r **************** \
-n \
—executor shell \
—tag-list «deploy,staging,production»\
—name «Deploy Runner» && \
tail -f /var/log/yum.log
