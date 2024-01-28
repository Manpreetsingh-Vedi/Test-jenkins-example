Jenkins Pipelines Generator
111
                echo 'This path is available from the ARTIFACTS environment variable.'
112
            }
113
        }
114
        // Octopus requires files to have a specific naming format. So copy the original artifact into a file with the correct name.
115
        sh(script: 'cp ${ORIGINAL_ARTIFACT} ${ARTIFACTS}')
116
      }
117
    }
118
    stage('Deployment') {
119
      steps {
120
        // This stage assumes you perform the deployment with Octopus Deploy.
121
        // The steps shown below can be replaced with your own custom steps to deploy to other platforms if needed.
122
        octopusPushPackage(additionalArgs: '',
123
          packagePaths: env.ARTIFACTS.split(":").join("\n"),
124
          overwriteMode: 'OverwriteExisting',
125
          serverId: params.ServerId,
126
          spaceId: params.SpaceId,
127
          toolId: 'Default')
128
        octopusPushBuildInformation(additionalArgs: '',
129
          commentParser: 'GitHub',
130
          overwriteMode: 'OverwriteExisting',
131
          packageId: env.ARTIFACTS.split(":")[0].substring(env.ARTIFACTS.split(":")[0].lastIndexOf("/") + 1, env.ARTIFACTS.split(":")[0].length()).replaceAll("\\." + env.VERSION_SEMVER + "\\..+", ""),
132
          packageVersion: env.VERSION_SEMVER,
133
          serverId: params.ServerId,
134
          spaceId: params.SpaceId,
135
          toolId: 'Default',
136
          verboseLogging: false,
137
          gitUrl: env.GIT_URL,
138
          gitCommit: env.GIT_COMMIT,
139
          gitBranch: env.GIT_BRANCH)
140
        octopusCreateRelease(additionalArgs: '',
141
          cancelOnTimeout: false,
142
          channel: '',
143
          defaultPackageVersion: '',
144
          deployThisRelease: false,
145
          deploymentTimeout: '',
146
          environment: params.EnvironmentName,
147
          jenkinsUrlLinkback: false,
148
          project: params.ProjectName,
149
          releaseNotes: false,
150
          releaseNotesFile: '',
151
          releaseVersion: env.VERSION_SEMVER,
152
          serverId: params.ServerId,
153
          spaceId: params.SpaceId,
154
          tenant: '',
155
          tenantTag: '',
156
          toolId: 'Default',
157
          verboseLogging: false,
158
          waitForDeployment: false)
159
        octopusDeployRelease(cancelOnTimeout: false,
160
          deploymentTimeout: '',
161
          environment: params.EnvironmentName,
162
          project: params.ProjectName,
163
          releaseVersion: env.VERSION_SEMVER,
164
          serverId: params.ServerId,
165
          spaceId: params.SpaceId,
166
          tenant: '',
167
          tenantTag: '',
168
          toolId: 'Default',
169
          variables: '',
170
          verboseLogging: false,
171
          waitForDeployment: true)
172
      }
173
    }
174
  }
175
}
BUILT BY OCTOPUS. HAPPY DEPLOYMENTS!
